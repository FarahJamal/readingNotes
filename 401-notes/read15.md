## optional reading ^^
# What Is Password Hashing?
### **TL;DR**
 Hash is both a noun and a verb. Hashing is the act of converting passwords into unreadable strings of characters that are designed to be impossible to convert back, known as hashes. Some hashing schemes are more easily cracked than others.
 
 ![](https://www.memecreator.org/static/images/memes/4956300.jpg)
 # Hashing in Action: Understanding bcrypt

 - The bcrypt hashing function allows us to build a password security platform that scales with computation power and always hashes every password with a salt.

 - the Best way to store passwords is to add a salt to the hashing process: adding additional random data to the input of a hashing function that makes each password hash unique. The ideal authentication platform would integrate these two processes, hashing and salting, seamlessly.

    + SHA families is that they were designed to be computationally fast.

# What is bcrypt?

- bcrypt was designed by Niels Provos and David Mazières based on the Blowfish cipher>): b for Blowfish and crypt for the name of the hashing function used by the UNIX password system.


- Another benefit of bcrypt is that it requires a salt by default. Let's take a deeper look at how this hashing function works!

```    "`bcrypt` forces you to follow security best practices as it requires a salt as part of the hashing process. Hashing combined with salts protects you against rainbow table attacks! Are password salts part of your security strategy?" ```

# JBCrypt
- jBCrypt is an implementation the OpenBSD Blowfish password hashing algorithm, as described in "A Future-Adaptable Password Scheme" by Niels Provos and David Mazieres.
- This system hashes passwords using a version of Bruce Schneier's Blowfish block cipher with modifications designed to raise the cost of off-line password cracking. The computation cost of the algorithm is parameterised, so it can be increased as computers get faster.



- **A simple example that demonstrates most of the features:**
```
// Hash a password for the first time
String hashed = BCrypt.hashpw(password, BCrypt.gensalt());

// gensalt's log_rounds parameter determines the complexity
// the work factor is 2**log_rounds, and the default is 10
String hashed = BCrypt.hashpw(password, BCrypt.gensalt(12));

// Check that an unencrypted password matches one that has
// previously been hashed
if (BCrypt.checkpw(candidate, hashed))
	System.out.println("It matches");
else
	System.out.println("It does not match");

  ```
😂😂
  ![](https://funvizeo.com/media/memes/8cb6f0588aeb238e/protected-encrypted-removable-personal-encrypted-personal-293ff9b8c6bce3c5-d0a057c6e730b090.jpg)