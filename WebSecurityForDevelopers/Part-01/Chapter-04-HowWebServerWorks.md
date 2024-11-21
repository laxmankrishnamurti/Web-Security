# Chapter :: 04 :: How Web Servers Work?

A _web server_ is a computer program that sens back _HTML pages or appropriate resources_ in response to HTTP requests.

Web servers serve two types of content in response to HTTP requests:

1. **Static resources**

   - Files that the web server returns unaltered in HTTP response. Web servers dosen't have to do any extra work in order to send thse files
     - HTML file
     - Images
     - Other static files

2. **Dynamic resources**
   - As per their name suggest, whenever an HTTP request come to a web server it first process the code, a script, or a template and executes or interprets and send the final result to the client.

- Modern web servers are capable of hosting both static and dynamic resources.
- Which resource the server executes or returns depends on the URL in the HTTP request.
- Every resources that are on the internet accessed by URL.
- URL is the location of a particular content
- When we enter the URL on the browser's address bar and hit enter it makes a HTTP request to the server which is hosting the resource and returns the appropriate file/resource from disk.
- Web server can link or unlink a particular resources to URL.
- Web server often dynamically compress large resource files by using the _gzip algorithm_ to reduce the bankwidth used in the response, or add caching headers in HTTP response to instruct the browser to cache and use a local copy of a static resources if a user views it again within a defined window of time.

**Potential Bugs :: The process of resolving a URL to a file can introduce vulnerabilities.**
**Potential Bugs :: The dynamic interpolation of content into the HTML can be vulnerable to attack.**

## CDN (Content delivery network)

- This is a modern innovation
- Designed to improve the delivery speed of static files.
- Which will store duplicated copies of static resources in data centers around the world, and quickly deliver those resource to browsers from the nearest physical location.

**Ex:- Cloudflare, Akamai, Amazon CloudFront**

- They offload the burden of serving large resources files, such as images, videos, to a third party.
- These **CDN** services charge a monthly fee depending on the amount of resources we deploy.
- Using a **CDN** also introduces security complications. Integrating with a **CDN** effectively allows a third party to serve content under our security certificate, so we need to set up our **CDN** integration securely.
  tre1

## Templates

- The first dynamic resources were simple _script_ file often written in the _Perl_ language.
- Making changes to Perl code while keeping in mind what the eventual rendered output will look like is a difficult task.
- To address this, web developers often use template files to build dynamic web pages.
- _Templates_ are mostly HTML, but have programmatic logic interspersed within then that contains instructions to the web server.

- This logic is simple and usually does one of three things:
  - Pull data from a database or the HTTP request
  - Interpolate it into the HTML
  - Conditionally render sections of the HTML template.

**Ex:- EJS (Embedded JavaScript Template)**

## Database

When a web server executes the code in a dynamic resource, it often loads data from a database. Database technology predates the invention of the web. As computers became more widespread back in the 1960s, companies started to see the value of digitizing and centralizing their record keeping to make searching and maintenance easier.

1. Relation Database
   - MySQL
   - Oracle
   - .....etc
2. Non-Relational Database

   - MongoDB
   - Cassendra
   - ......etc

3. Distributed Caches

   - Dynamic resources can also load data from in-memory distributed _caches_, another popular approach to achieving the massive scalability required by large websites.

   - Caching referes to the process of storing a copy of data kept elsewhere in an easily retrievable from, to speed up retrieval of that data.

   - Ex :: Redis, Memcached, ....etc

   - Distributed caches can be shared among web servers, making them ideal for storing frequently accessed data that would otherwise have to be retrieved from a database.

## Web programming languages

- **Ruby (on Rails)**
- **Python**
- **JavaScript and Node.js**
- **PHP**
- **JAVA**
- **C#**
- **C#**

## Client-Side JavaScript

When our code need to be executed in the browser, we have exactly one choice: JavaScript.

Achieving dynamic user interface without refreshing the whole page and interrupting the user experience requires client-side JavaScript to manage a lo of state in memory.

Several frameworks have been developed to organized memory state and render pages efficiently. They also allow for modular reuse of JavaScript code over various pages on the site, a key design consideration when we have millions of line of JavaScript to manage.

- JavaScript frameworks

  - Angular (Originally released by Google)

    - Follows server-side paradigms
    - As the memory state state changes, Angular automatically re-renders the DOM. This separation makes for cleaner code and more-maintainable web applications.

  - React (Originally released by Facebook)
    - Follows JSX style

**Potential bugs :: DOM-based cross-site scripting attacks**

We can also use _CoffeeScript or TypeScript_ that are _transpiled_ into JavaScript during the build process before being sent to the browser.

These languages are subject to the same security vulnerabilities as JavaScript at execution time.
