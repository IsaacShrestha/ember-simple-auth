# Introduction

Ember-simple-auth is a open-source project available in github. It is a lightweight plugin to implement authentication in EmberJS applications. EmberJS is an open-source JavaScript framework for web development. 

Ember-simple-auth consists of 4 main building blocks - the session, a session store, authenticators and authorizers. The session service is the main interface that provides methods for authentication and invalidating the session. It also sets and reads the session data. The session store persists the session state; authenticators authenticate the session; and authorizers use the data retrieved by an authenticator and stored in the session to generate authorization data.

* __Contributors__: This plugin is developed by simplabs GmbH/Marco Otte-Witte and contributors. There are total 169 contributors for this project till now with one contributor having 1,733 commits and four contributors having more than 500 commits. Other contributors also have made significant improvements to the project. At present there are 37 open issues, 878 closed issues and 12 pull requests.

* __Activity__: The project is actively accepting pull requests. Most of the open issues and pull requests have comments in them of some sorts even if they are not accepted which says that the community provides good support and guidance.

* __Use__: It is a lightweight plugin which can be used with any EmberJS applications to implement authentication. Heroku, Ghost, Runtastic, Krit and Crowdly are some of the companies using Ember-simple-auth.

* __Popularity__: This repository has been forked 523 times. It has 169 contributors and well over 2,000 commits. Since, It can support all kinds of authentication and authorization mechanisms in EmberJS applications so are widely preferred while building web applications with Emberjs.

* __Languages used__: JavaScript (97%), HTML (2.6%) and CSS (0.1%)

* __Platform__: JavaScript platform, EmberJS framework

* __Document sources__: http://ember-simple-auth.com/api/

  * __About Ember-simple-auth__ 
      https://github.com/simplabs/ember-simple-auth/tree/1.4.0#readme 
  
  * __API documentation__ 
      http://ember-simple-auth.com/api/ 

  * __Source repository__ 
      https://github.com/simplabs/ember-simple-auth 

  * __Issue tracking__
      https://github.com/simplabs/ember-simple-auth/issues 

  * __Installation and user guide__
      https://github.com/simplabs/ember-simple-auth/tree/1.4.0#installation 


# License, Procedures for making contributions and Contributor agreements

Ember Simple Auth is developed by simplabs [GmbH/Marco Otte-Witte](http://simplabs.com/) and contributors. It is released under the [MIT License](https://github.com/simplabs/ember-simple-auth/blob/master/LICENSE)

## MIT License
License means the terms and conditions for use, reproduction and distribution. Any contribution to the project can be made abiding with the terms and conditions mentioned in the license document. Nothing mentioned in the license document can supersede or modify the terms of any separate license agreement that has been made between an individual or legal entity and the licensor. This project has MIT license and is free to use, copy, modify, merge, publish, distribute, sublicense, and/or sell the copies of the Software. This copyright and notice permission should be included in all copies or substantial portions of the plugin. It is provided “As Is”, without any warranty of any kind.

## Procedures for making contributions
__Reporting Issues__:
  * Issues should be created only bugs, feature requests etc.
  * Update to the latest release of Ember Simple Auth.
  * Update to the latest releases of EmberJS, jQuery, Ember Data if possible.
  * Include as much information as possible - this includes full stack traces etc.
  * Set up a demo that demonstrates the issue on JSFiddle or JSBin.
  
__Pull Requests__:
  * Fork the repository and implement changes.
  * Run the tests - pull requests with failing tests are not accepted.
  * Adhere to Ember-simple-auth's coding style
  * Squash all commits into one before submitting.
  * Provide a good description for the pull request - what does it add?, why is that needed?, etc.
  
 __Run Tests__:
   * Fork the repository.
   * Run yarn install and bower install.
   * Install PhantomJS to run the tests.
   * To run tests against the currently installed Ember version, run ember test.
   * To simulate a CI run: run yarn test && yarn run test:node.
 
 ## Contributor agreements
 The project is accepting pull requests. There are 13 open pull requests right now as well as 511 closed pull requests. 


# Security related history

__Vulnerability__: Regular Expression Denial of Service (DoS)

__Vulnerable module__: minimatch

Minimatch is a minimalistic matching library used for converting glob expression into JavaScript RegExp objects. Affected versions of this package are vulnerable to Regular Expression Denial of Service attack. 

Regular Expression Denial of Service Attack is a type of Denial of Service attack in which many Regular Expression implementations may reach edge cases that causes them to work very slowly, allowing an attacker to exploit this and can cause the program to enter these extreme situations by using a Regex string and case the service to hang for a large periods of time. 

__Vulnerability__: Cross-site scripting (XSS)

Session information is stored in local storage. If the applications using Ember-simple-auth is XSS vulnerable than the session information can be read by the attacker. 


# Functional security requirements for the software

The requirements are mapped to Ember-simple-auth’s API. Ember-simple-auth provides various classes to use. These functional requirements are related to session management,  authentication, authorization and encryption.

1. __Context__: Session Management

Ember-simple-auth stores a session cookies, by default on closing the browser session cookies are expired and deleted. However, users can configure cookie expiration period and store session persistently by selecting “Remember me”, which makes it prone to session hijacking. 

  * Functional security requirements:
    * The system is expected to delete the stored session cookies.
    * The system  is expected to persist data upon using persist function.
    
2. __Context__: Authentication, Authorization and Encryption

Ember-simple-auth defines several methods for checking session authentication,  such as authentication succeeded and invalidation succeeded. Ember-simple-auth requires session to be authenticated in order to authorize.

 * Functional security requirements:
   * The system is expected to provide access to routes only to authenticated session.
   * The system is expected allow authorization to authorized user with authenticated session.
   * The system is expected to encrypt session cookies to protect the from security attacks like session hijacking.


# Motivation for selecting this project

__Keywords__: Familiarity, lightweight javascript, popularity
 > It has minimal requirements with respect to application structure, routes etc. With its pluggable strategies it can support all kinds of authentication and authorization mechanism.
 
The above description is from Ember-simple-auth’s official website, which caught our attention, specifically in aspects of “minimal requirements” required and ability to “support for all kind of authentication and authorization mechanism”, viewing this from security point of view, this library seemed a perfect candidate for software assurance project. 

Ember-simple-auth is one of the popular library for implementing authentication in projects developed using EmberJS framework. It has been used in ghost, runtastic, heroku, krit, crowdly. Our familiarity with JavaScript, concepts related to session management and authentication was our key motivator. Small size of the Ember-simple-auth will help us to understand moving parts of this JavaScript library in a better depth. In addition to that, the community maintaining Ember-simple-auth  is active and is willing to accept contributions.



# Requirements for Software Security Engineering

## List of final assurance claims

[Assurance claims](https://www.lucidchart.com/invitations/accept/4e43aec6-1320-466d-a5ff-15d2dc5eb8dd)

1. Ember simple auth provides acceptably sufficient security against session hijacking.
2. Ember simple auth provides sufficient security against injection attacks to ember applications.
3. Ember simple auth reduces instances of insufficient authorizations.
4. Ember simple auth authentication mechanisms are acceptably secure for ember applications.
5. Ember simple auth sufficiently protects secret information from getting exposed to third parties. 

## The security requirements for the project captured using misuse case diagrams

[Misuse cases](https://www.lucidchart.com/invitations/accept/b39daaf5-cecb-4ba8-9401-0331b2b090a1)

__Misuse case__: Session Hijacking

...__Security requirement 1__: Encrypting session tokens

...In order to prevent session hijacking attacks, session tokens should be strongly encrypted. 

...__Security requirement 2__: Invalidating session tokens periodically

...The attackers may steal session tokens and use it to access critical information as a verified user. In order to mitigate stealing of ...session tokens, existing session tokens need to be invalidated and new session tokens should be generated periodically.

...__Security requirement 3__: Making the session data read-only

...The attackers may set user’s session data to the one known to him which is also known as session fixation. This attack can be ...prevented by making the session data read-only. If the session data are read-only then the attackers cannot set/write user’s session ...id as the one known to him. 

...__Security requirement 4__: Authenticating session token

The attackers may access critical information if they access user’s session token. In order to prevent unauthorized access, the new session token must be generated periodically and they must be authenticated in each event initiated by the user.

__Security requirement 5__: Accepting session token only from valid source

The attackers may send session tokens that are previously known to them in order to access the application. To prevent this, ember simple auth should accept tokens from from valid sources.


__Misuse case__: Injection attacks

__Security requirement 6__: Sanitizing user inputs

Since, ember simple auth accepts user input to allow them to register and login, it might be prone to injection attacks. To prevent this attack, the user inputs should be sanitized as soon as they are provided by the users.


__Misuse case__: DOS attacks

__Security requirement 7__: Using captcha

While registering users through ember simple auth, the attackers can use bots to produce massive amount of registration requests. This can lead to denial of service to other users. In order to prevent this attack, ember simple auth should provide provision of using captcha to confirm if the users are not a bot.


## Alignment of security requirements with advertised features in Ember simple auth documentation
The alignment of security requirements with the advertised features in the documentation are presented below:

__Security requirement 1__: Encrypting session tokens

__Addressed by the documentation?__ No

[Source](https://github.com/simplabs/ember-simple-auth#authorizers)

Session token / Session ID is used to uniquely identify user sessions on the server, This  session token can have various format, ranging from simple text to encoded string. Ember Simple Auth does not mention any feature that can be used to encrypt session tokens.However, we can workaround using existing features. User can create their own encryption mechanism and then create a custom authorizer to process encrypted session tokens, we can recommend this alternative method as an improvement to the documentation  Ember simple auth’s documentation on github provides examples to implement custom authorization.

__Security requirement 2__: Invalidating session tokens periodically

__Addressed by the documentation?__ No

[Source](https://ember-simple-auth.com/api/classes/ApplicationRouteMixin.html)

Ember simple auth’s documentation does not mention about any features that provide the functionality to invalidate session token periodically. Usually, properties of session token varies from application to application, It is upto application how they define it.
However, the documentation mentions of methods such as invalidateSession(), which can be creatively used to perform the required need. Perhaps, this use of the invalidateSession()can be recommended as feature improvement.

__Security Requirement 3__: Making the session data read-only

__Addressed by the documentation?__ Yes

[Source](https://github.com/simplabs/ember-simple-auth#the-session-service)

Ember simple auth’s documentation mentions that “While the special authenticated section in the session data contains the data that was acquired by the authenticator when it authenticated the session and is read-only”

__Security Requirement 4__: Authenticating session token

__Addressed by the documentation?__ Yes

[Source](https://github.com/simplabs/ember-simple-auth#authenticators)

Ember simple auth’s documentation mentions about variety of authenticators and their feature and implementation ideas.

__Security Requirement 5__: Accepting session token only from valid source

__Addressed by the documentation?__ No

Ember simple auth’s documentation does not mention any feature that can ensure that session accepted should originate from valid source. However, this can be recommended as a feature improvement.

__Security Requirement 6__: Sanitizing user inputs

__Addressed by the documentation?__ No

Ember simple auth’s documentation does not mention any features to sanitize user inputs.We are uncertain, if Ember Simple Auth consider this feature is out of their scope to implement. And they left this implementation to developers of ember app.

__Security Requirement 7__: Using captcha 

__Addressed by the documentation?__ No

Ember Simple Auth’s documentation does not mention ‘captcha’ as their authentication feature. Captcha for authentication perhaps might be implemented through ember-simple-auth’s one of the many authenticators(for eg: Oauth2 , Devise, Torii), but the documentation does not mention of any detailed authentication features that can be implemented through their available authenticators.
We can recommend to improve the documentation by listing the available authentication features of authenticators provided by ember simple auth.

## Security related configuration and installation issues in Ember simple auth documentation

1. Installation guide

Proper documentation for installation along with link to dummy application that shows how it should function after correct installation.

2. Inject session service

After installation ember simple auth needs to inject session service wherever required in the application, and also handle the display of login and logout button based on current state. Documentation contains good explanation of this and also guide how to do it by providing code examples.

3. Authenticators and authorizers
[Source](https://github.com/simplabs/ember-simple-auth#authenticators)

The documentation explains how the current session token can be authenticated. It can use various authentication mechanism like OAuth2, Devise Authenticator, and Torri Authenticator. It also explains how these authenticators can be used. However, it doesn’t explain about the security requirements while using these authenticators. Although, these authenticators are  popular but they do not guarantee a request’s confidentiality, which could lead to several threats such as eavesdropping. By mentioning this in the documentation and asking users to use secure connection such as SSL can be a mitigating measure for this issue. We plan to open an issue related to this in ember simple auth OSS community and request them to update it in their documentation.  

4. Failure in specific browers like Safari

Web application using ember simple auth fails in safari when private browsing is turned on with a QuotaExceededError. The easiest fix to this would be using custom store that extends SimpleAuth.Stores.LocalStorage. This is already a closed issue but the fixation or warning of this issue is not mentioned in the documentation. We would request the ember simple auth community to mention this in their documentation and aware future users. 

