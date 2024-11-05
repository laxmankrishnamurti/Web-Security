# Why?

Because most internet users interact with websites through a browser. So, it's a must to know how browsers work to build a secure website. Let's get started........

# What a brower does?

In short, browsers does these two main important thing

1. Fetch the resources which we want, over the internet
2. Rendered the resource on the webpage.

Yes, these are the two main important task that a browser is used for. Let's understand one-by-one.

# Fetching the resources that we request over the internet.

1. We hit url or any keyword in the search bar or address bar.
2. If it is a URL, first of all browser resolve the domain name to an IP address and go to the server and request the resources which we want from the server. Browser map the domain name to their respective IP address with the help of :-

- Operating system's DNS cache
- ISP DNS cache
- Authoritative DNS server.

3. If we enter any keyword or a string in the address bar or in the search bar, the browser's search engine search the similar keyword over the internet and shows the best possible result on the page along with the website, when we click on any link it will do the same as it does with the URL.

4. Server will respond back and send appropriate result.

5. Browser receive the response and render it to the webpage in visual representation.

In short, browser used for making HTTP request over the internet and helps to find out the particular resources on the internet.

# Rendering webpage

Browser is just a software which consists:

1. Search Engine(V8 in chrome, spidermonkey in firefox) ==> Used to find out the resorces over the internet.
2. Rendering pipeline ==> Responsible for rendering webpage.

## Rendering Pipeline ?

The software component within a web browser that's responsible for transforming a web page's HTML into the visual representation which we see onscreen, is called the _rendering pipeline._

It is responsible for:

- parsing the HTML page.
- Understand the structure and the content of the document, and converting it to a series of drawing operations that the operating system can understand.

## What HTML exactly is ?

HTML was envisioned as a _markup language_, meaning it described the web page by breaking it into semantic elements and annotating how the information was structured.

## The Document Object Model

Browser receives an HTTP response containing HTML ===> Parse ===> Into a DOM.

1. DOM ===> DOM is basically a _data structure_ describing the HTML document as a series of nested elements. Each element in the DOM is called a DOM node.

DOM nodes can contain text content, or contain other DOM nodes, means each node can contain other nodes in a branching fashion.

2. If node contains any script, videos, or external URL, browser makes a HTTP request and does the same as previous one which we already discussed.

3. They close unclose tags, insert missiing tags, and ignore corrupted tags as needed.
4. Finally it will loaded in the memory (RAM)

```js
- document object model structure
  - node
    - text content
    - other nodes
  - script node
    - HTTP request
    - download the resource
    - load into the dom

  - close unclose tags, insert missing tags, ignore corrupted tags

- Finally load the drawing or the data structure into the main memory
```

## Styling information

Web developer will create one or more _stylesheets_ to declare how elements on the page should be rendered. The HTML document import will import these stylesheets by using a _<style></style>_ tag referencing the external URL that hosts the stylesheet.

The rendering pipeline implements a lot of logic to decipher final styling.

<code>The construction of the DOM tree and the application of styling rules occur in parallel to the processing of any JavaScript code contained in the web page. This JavaScript code can change the sturcute and layout of the page even before it's rendered.</code>

## JavaScript

A fully fledged programming language that is executed by the browser's JavaScript engine when web pages are rendered.

<code>By default, any JavaScript code is executed by the browser as soon as the relevant _script_ tag is parsed into a DOM node. For JavaScript code loaded from an external URL, this means the code is executed as soon as it is loaded. </code>

This default behaviour causes problems if the rendering pipeline hasn't finished parsing the HTML document; the JavaScript code will attempt to interact with page element that may not yet exists in the DOM. To allow for this, _script_ tags are often marked with a **_defer_** attribute.

## Security Issues

As we would imagine, the fact that browsers eagerly execute any JavaScript code they come across has security implications. A hacker's end goal is often the remote execution of code on another user's machine.

For this reason, modern browsers heavily restrict JavaScript with the browser security model. This dictates that JavaScript code must be executed within a sandbox, **_*where it's not permitted to perform any of the following actions:*_**

1. Start new process or access other existing processes.
2. Read arbitrary chunks of system memory. As a managed memory language, JavaScript can't read memory outside its sandbox.
3. Access the local disk. Modern browsers allow websites to store small amounts of data locally, but this storage is abstracted from the file system itself.
4. Access the operating system's network layer.
5. Call operating system functions.

**_*JavaScript executing in the browser sandbox is permitted to do the following actions:*_**

1. Read and manipulate the DOM of the current web page.
2. Listen to and respond to user actions on the current page by registering event listeners.
3. Make HTTP calls on behalf of the user.
4. Open new web pages or refresh the URL of the current page but only in response to a user action.
5. Write new entries to the browser history and go backward and forward in history.
6. Ask for the users' location. For example, "Google Maps would like to use your location."
7. Ask permissions to send desktop notification.

<code>Even though with these restrictions an attacker can inject malicious JavaScript into web page can still do a lot of harm by using _cross-site scripting_</code>

## Rendering full process

- Response as HTML
- Parsed into DOM
- Loaded into RAM(chunks of drawing into semantic tags)
- Styling
- JavaScript Code Execution(if script tag is loaded)
- Parallely(DOM, Styling, JavaScript code execution)
- A blank web-page will rendered by the browser to arrange all drawings based on their sytling.

- JavaScript
  - Interact with DOM document and make changes
  - Make HTTP request.

# Other tasks that a browser does.

1. Browser connect with the operating system to resolve and cache DNS addresses.
2. Interpret and verify security certificates, encode requests in HTTPS.
3. Store and transmit cookies.
   `
