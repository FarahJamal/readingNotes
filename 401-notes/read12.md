# Spring RESTful Routing & Static Files

## RequestMapping Basics
Requisting mapping doen by the following methods 

1. RequestMapping — by Path

Syntax

```
@RequestMapping(value = "/ex/foos", method = RequestMethod.GET)
@ResponseBody
public String getFoosBySimplePath() {
    return "Get some Foos";
}
```
To test out this mapping with a simple curl command, run:

curl -i http://localhost:8080/spring-rest/ex/foos

2. RequestMapping — the HTTP Method

Note: The HTTP method parameter has no default. So, if we don't specify a value, it's going to map to any HTTP request.

```
@RequestMapping(value = "/ex/foos", method = POST)
@ResponseBody
public String postFoos() {
    return "Post some Foos";
}
```

To test the POST via a curl command:

```
curl -i -X POST http://localhost:8080/spring-rest/ex/foos
```

3. RequestMapping and HTTP Headers

3.1 RequestMapping With the headers Attribute

```
@RequestMapping(value = "/ex/foos", headers = "key=val", method = GET)
@ResponseBody
public String getFoosWithHeader() {
    return "Get some Foos with Header";
}
```

To test the operation, we're going to use the curl header support:

```
curl -i -H "key:val" http://localhost:8080/spring-rest/ex/foos
```

3.2 Consumes and Produces

Mapping media types produced by a controller method is worth special attention.

```
@RequestMapping(
  value = "/ex/foos", 
  method = GET, 
  headers = "Accept=application/json")
@ResponseBody
public String getFoosAsJsonFromBrowser() {
    return "Get some Foos with Header Old";
}
```

4. RequestMapping With Path Variables

4.1  Single @PathVariable

Syntax:

```
@RequestMapping(value = "/ex/foos/{id}", method = GET)
@ResponseBody
public String getFoosBySimplePathWithPathVariable(
  @PathVariable("id") long id) {
    return "Get a specific Foo with id=" + id;
}
```

This can be tested with curl:

```
curl http://localhost:8080/spring-rest/ex/foos/1
```

4.2 Multiple @PathVariable

Syntax:

```
@RequestMapping(value = "/ex/foos/{fooid}/bar/{barid}", method = GET)
@ResponseBody
public String getFoosBySimplePathWithPathVariables
  (@PathVariable long fooid, @PathVariable long barid) {
    return "Get a specific Bar with id=" + barid + 
      " from a Foo with id=" + fooid;
```
This is easily tested with a curl in the same way:


```
curl http://localhost:8080/spring-rest/ex/foos/1/bar/2
```

5. RequestMapping With Request Parameters

6. RequestMapping Corner Cases

7. New Request Mapping Shortcuts

8.  Spring Configuration

## Accessing Data with JPA

 I will walks you through the process of building an application that uses Spring Data JPA to store and retrieve data in a relational database.

 The link below will guide you to build you app 

[link](https://spring.io/guides/gs/accessing-data-jpa/)

## CrudRepository, JpaRepository, and PagingAndSortingRepository in Spring Data

1. Spring Data Repositories

Each of these defines its own functionality:

CrudRepository provides CRUD functions
PagingAndSortingRepository provides methods to do pagination and sort records
JpaRepository provides JPA related methods such as flushing the persistence context and delete records in a batch

3. CrudRepository

Notice the typical CRUD functionality:

save(…) – save an Iterable of entities. Here, we can pass multiple objects to save them in a batch
findOne(…) – get a single entity based on passed primary key value
findAll() – get an Iterable of all available entities in database
count() – return the count of total entities in a table
delete(…) – delete an entity based on the passed object
exists(…) – verify if an entity exists based on the passed primary key value

3. PagingAndSortingRepository