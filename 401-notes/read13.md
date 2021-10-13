# Related Resources and Integration Testing

## Working with Relationships in Spring Data REST

1. One-to-One Relationship

1.1 The Data Model

define two entity classes Library and Address having a one-to-one relationship, using the @OneToOne annotation.

```
@Entity
public class Library {
    @Id
    @GeneratedValue
    private long id;
    @Column
    private String name;
    @OneToOne
    @JoinColumn(name = "address_id")
    @RestResource(path = "libraryAddress", rel="address")
    private Address address;
    
    // standard constructor, getters, setters
}
```

- The @RestResource annotation is optional and can be used to customize the endpoint.

- We must be careful to have different names for each association resource. Otherwise, we will encounter a JsonMappingException with the message: “Detected multiple association links with same relation type! Disambiguate association”.

- The association name defaults to the property name and can be customized using the rel attribute of @RestResource annotation:

```
@OneToOne
@JoinColumn(name = "secondary_address_id")
@RestResource(path = "libraryAddress", rel="address")
private Address secondaryAddress;
```

1.2 The Repositories

let's create two repository interfaces for each of them, by extending the CrudRepository interface:
```
public interface LibraryRepository extends CrudRepository<Library, Long> {}
public interface AddressRepository extends CrudRepository<Address, Long> {}
```

- add a Library instance to work with:

```
curl -i -X POST -H "Content-Type:application/json" 
  -d '{"name":"My Library"}' http://localhost:8080/libraries
```

- The API returns the JSON object:

```
{
  "name" : "My Library",
  "_links" : {
    "self" : {
      "href" : "http://localhost:8080/libraries/1"
    },
    "library" : {
      "href" : "http://localhost:8080/libraries/1"
    },
    "address" : {
      "href" : "http://localhost:8080/libraries/1/libraryAddress"
    }
  }
}
```
1.4 Creating the Associations
After persisting both instances, we can establish the relationship by using one of the association resources.

This is done using the HTTP method PUT, which supports a media type of text/uri-list, and a body containing the URI of the resource to bind to the association.

Since the Library entity is the owner of the association, let's add an address to a library:

```
curl -i -X PUT -d "http://localhost:8080/addresses/1" 
  -H "Content-Type:text/uri-list" http://localhost:8080/libraries/1/libraryAddress
```

2. One-to-Many Relationship
A one-to-many relationship is defined using the @OneToMany and @ManyToOne annotations and can have the optional @RestResource annotation to customize the association resource.

2.1 The Data Model

Syntax

```
@Entity
public class Book {
    @Id
    @GeneratedValue
    private long id;
    
    @Column(nullable=false)
    private String title;
    
    @ManyToOne
    @JoinColumn(name="library_id")
    private Library library;
    
    // standard constructor, getter, setter
}
```

Let's add the relationship to the Library class as well:

```
public class Library {
 
    //...
 
    @OneToMany(mappedBy = "library")
    private List<Book> books;
 
    //...
 
}
```

2.2 The Repository

We also need to create a BookRepository:

```
public interface BookRepository extends CrudRepository<Book, Long> { }
```

2.3 The Association Resources

In order to add a book to a library, we need to create a Book instance first by using the /books collection resource:

```
curl -i -X POST -d "{\"title\":\"Book1\"}" 
  -H "Content-Type:application/json" http://localhost:8080/books
```

3. Many-to-Many Relationship
A many-to-many relationship is defined using @ManyToMany annotation, to which we can add @RestResource.

3.1  The Data Model

To create an example of a many-to-many relationship, let's add a new model class Author that will have a many-to-many relationship with the Book entity:

Syntax 

```
@Entity
public class Author {
    @Id
    @GeneratedValue
    private long id;
    @Column(nullable = false)
    private String name;
    @ManyToMany(cascade = CascadeType.ALL)
    @JoinTable(name = "book_author", 
      joinColumns = @JoinColumn(name = "book_id", referencedColumnName = "id"), 
      inverseJoinColumns = @JoinColumn(name = "author_id", 
      referencedColumnName = "id"))
    private List<Book> books;
    //standard constructors, getters, setters
}
```

3.2 The Repository

Let's create a repository interface to manage the Author entity:

```
public interface AuthorRepository extends CrudRepository<Author, Long> { }
```

4.3 The Association Resources

As in the previous sections, we must first create the resources before we can establish the association.

Let's first create an Author instance by sending a POST requests to the /authors collection resource:

```
curl -i -X POST -H "Content-Type:application/json" 
  -d "{\"name\":\"author1\"}" http://localhost:8080/authors
```

Next, let's add a second Book record to our database:

```
curl -i -X POST -H "Content-Type:application/json" 
  -d "{\"title\":\"Book 2\"}" http://localhost:8080/books
```

5. Testing the Endpoints With TestRestTemplate

Let's create a test class that injects a TestRestTemplate instance and defines the constants we will use:

```
@RunWith(SpringRunner.class)
@SpringBootTest(classes = SpringDataRestApplication.class, 
  webEnvironment = WebEnvironment.DEFINED_PORT)
public class SpringDataRelationshipsTest {
    @Autowired
    private TestRestTemplate template;
    private static String BOOK_ENDPOINT = "http://localhost:8080/books/";
    private static String AUTHOR_ENDPOINT = "http://localhost:8080/authors/";
    private static String ADDRESS_ENDPOINT = "http://localhost:8080/addresses/";
    private static String LIBRARY_ENDPOINT = "http://localhost:8080/libraries/";
    private static String LIBRARY_NAME = "My Library";
    private static String AUTHOR_NAME = "George Orwell";
```
4.1 Testing the One-to-One 

Let's create a @Test method that saves Library and Address objects by making POST requests to the collection resources.

Then it saves the relationship with a PUT request to the association resource and verifies that it has been established with a GET request to the same resource:

```
@Test
public void whenSaveOneToOneRelationship_thenCorrect() {
    Library library = new Library(LIBRARY_NAME);
    template.postForEntity(LIBRARY_ENDPOINT, library, Library.class);
   
    Address address = new Address("Main street, nr 1");
    template.postForEntity(ADDRESS_ENDPOINT, address, Address.class);
    
    HttpHeaders requestHeaders = new HttpHeaders();
    requestHeaders.add("Content-type", "text/uri-list");
    HttpEntity<String> httpEntity 
      = new HttpEntity<>(ADDRESS_ENDPOINT + "/1", requestHeaders);
    template.exchange(LIBRARY_ENDPOINT + "/1/libraryAddress", 
      HttpMethod.PUT, httpEntity, String.class);
    ResponseEntity<Library> libraryGetResponse 
      = template.getForEntity(ADDRESS_ENDPOINT + "/1/library", Library.class);
    assertEquals("library is incorrect", 
      libraryGetResponse.getBody().getName(), LIBRARY_NAME);
```

4.2 Testing the One-to-Many Relationship
Let's create a @Test method that saves a Library instance and two Book instances, sends a PUT request to each Book object's /library association resource, and verifies that the relationship has been saved:

```
@Test
public void whenSaveOneToManyRelationship_thenCorrect() {
    Library library = new Library(LIBRARY_NAME);
    template.postForEntity(LIBRARY_ENDPOINT, library, Library.class);
    Book book1 = new Book("Dune");
    template.postForEntity(BOOK_ENDPOINT, book1, Book.class);
    Book book2 = new Book("1984");
    template.postForEntity(BOOK_ENDPOINT, book2, Book.class);
    HttpHeaders requestHeaders = new HttpHeaders();
    requestHeaders.add("Content-Type", "text/uri-list");    
    HttpEntity<String> bookHttpEntity 
      = new HttpEntity<>(LIBRARY_ENDPOINT + "/1", requestHeaders);
    template.exchange(BOOK_ENDPOINT + "/1/library", 
      HttpMethod.PUT, bookHttpEntity, String.class);
    template.exchange(BOOK_ENDPOINT + "/2/library", 
      HttpMethod.PUT, bookHttpEntity, String.class);
    ResponseEntity<Library> libraryGetResponse = 
      template.getForEntity(BOOK_ENDPOINT + "/1/library", Library.class);
    assertEquals("library is incorrect", 
      libraryGetResponse.getBody().getName(), LIBRARY_NAME);
}
```

5.3. Testing the Many-to-Many Relationship
For testing the many-to-many relationship between Book and Author entities, we will create a test method that saves one Author record and two Book records.
Then it sends a PUT request to the /books association resource with the two Books‘ URIs and verifies that the relationship has been established:

```
@Test
public void whenSaveManyToManyRelationship_thenCorrect() {
    Author author1 = new Author(AUTHOR_NAME);
    template.postForEntity(AUTHOR_ENDPOINT, author1, Author.class);
    Book book1 = new Book("Animal Farm");
    template.postForEntity(BOOK_ENDPOINT, book1, Book.class);
    Book book2 = new Book("1984");
    template.postForEntity(BOOK_ENDPOINT, book2, Book.class);
    HttpHeaders requestHeaders = new HttpHeaders();
    requestHeaders.add("Content-type", "text/uri-list");
    HttpEntity<String> httpEntity = new HttpEntity<>(
      BOOK_ENDPOINT + "/1\n" + BOOK_ENDPOINT + "/2", requestHeaders);
    template.exchange(AUTHOR_ENDPOINT + "/1/books", 
      HttpMethod.PUT, httpEntity, String.class);
    String jsonResponse = template
      .getForObject(BOOK_ENDPOINT + "/1/authors", String.class);
    JSONObject jsonObj = new JSONObject(jsonResponse).getJSONObject("_embedded");
    JSONArray jsonArray = jsonObj.getJSONArray("authors");
    assertEquals("author is incorrect", 
      jsonArray.getJSONObject(0).getString("name"), AUTHOR_NAME);
}
```

Subject|link
---|---
Related data in Spring (focus on the relationship annotations, not the curl requests)|[link1](https://www.baeldung.com/spring-data-rest-relationships#testing-the-endpoints-with-testresttemplate)
Baeldung: Spring Integration Testing|[link2](https://www.baeldung.com/integration-testing-in-spring)