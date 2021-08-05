## OAuth.

### What is OAuth?
**OAuth is an authentication protocol that allows you to approve one application interacting with another on your behalf without giving away your password.**

- example of OAuth:
  - The simplest example of OAuth in action is one website saying “hey, do you want to log into our website with other website’s login?”
  - ou can tell Facebook that it’s OK for Saraha.com to access your profile or post updates to your timeline without having to give ESPN your Facebook password.
  - our smart home devices – toaster, thermostat, security system, etc. – probably use some kind of login data to sync with each other and allow you to administer them from a browser or client device. These devices use what OAuth calls confidential authorization. That means they hold onto the secret key information, so you don’t have to log in over and over again.


## SAML vs. OAuth
|SAML|OAuth|
|---|---|
|uses XML to pass messages|OAuth uses JSON|
| geared towards enterprise security| provides a simpler mobile experience|
|SAML, on the other hand, drops a session cookie in a browser that allows a user to access certain web pages – great for short-lived work days, but not so great when have to log into your thermostat every day.|OAuth uses API calls extensively, which is why mobile applications, modern web applications, game consoles, and Internet of Things (IoT) devices find OAuth a better experience for the user|


## OAuth Explained:
![](https://blogvaronis2.wpengine.com/wp-content/uploads/2012/04/oauth-explained-1024x622.png)


## How Does OAuth Works:
There are 3 main players in an OAuth transaction: 
- the user (Joe)
- the consumer(Bitly)
- the service provider(Twitter)
  *  Twitter is the service provided who controls Joe’s secure resource (his Twitter stream)
  * Joe would like Bitly to be able to post shortened links to his stream.


 1- ***Step 1*** – The User Shows Intent

   - Joe (User): “Hey, Bitly, I would like you to be able to post links directly to my Twitter stream.”
   - Bitly (Consumer): “Great! Let me go ask for permission.”
    
    
2- **Step 2** – The Consumer Gets Permission

   - Bitly: “I have a user that would like me to post to his stream. Can I have a request token?”
   - Twitter (Service Provider): “Sure.  Here’s a token and a secret.”

3- **Step 3** – The User Is Redirected to the Service Provider

   - Bitly: “OK, Joe.  I’m sending you over to Twitter so you can approve.  Take this token with you.”
    - Joe: “OK!

4- **Step 4** – The User Gives Permission

   - Joe: “Twitter, I’d like to authorize this request token that Bitly gave me.”
  - Twitter: “OK, just to be sure, you want to authorize Bitly to do X, Y, and Z with your Twitter account?”
  -  Joe: “Yes!”
   - Twitter: “OK, you can go back to Bitly and tell them they have permission to use their request token.”

5-**Step 5** – The Consumer Obtains an Access Token

  -  Bitly: “Twitter, can I exchange this request token for an access token?”
  -  Twitter: “Sure.  Here’s your access token and secret.”

6-**Step 6** – The Consumer Accesses the Protected Resource

   - Bitly: “I’d like to post this link to Joe’s stream.  Here’s my access token!”
   - Twitter: “Done!”

**Note** that Joe never had to share his Twitter credentials with Bitly.  He simply delegated access using OAuth in a secure manner. 