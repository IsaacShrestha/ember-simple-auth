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
1. Ember simple auth provides acceptably sufficient security against session hijacking.
2. Ember simple auth provides sufficient security against injection attacks to ember applications.
3. Ember simple auth reduces instances of insufficient authorizations.
4. Ember simple auth authentication mechanisms are acceptably secure for ember applications.
5. Ember simple auth sufficiently protects secret information from getting exposed to third parties. 

[Assurance claims](https://www.lucidchart.com/invitations/accept/20f0a02c-81fe-4f89-b1a8-9bdeb7412fdb)

## The security requirements for the project captured using misuse case diagrams

__Misuse case__: Session Hijacking
__Security requirement 1__: Encrypting session tokens
In order to prevent session hijacking attacks, session tokens should be strongly encrypted. 





