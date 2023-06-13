# Sources and Sinks Cheatsheet

## Summary

This file contains common JavaScript sources and sinks that lead to potential vulnerabilities. All examples were taken from [PortSwigger](https://portswigger.net/ "PortSwigger Website") lessons on [Dom-Based vulnerabilities](https://portswigger.net/web-security/dom-based "Dom Based Vulnerabilities Lesson On PortSwigger").

---

## Contents

* [Summary](#summary "Jump To Section")

* [What Are Sources and Sinks?](#what-are-sources-and-sinks "Jump To Section")

* [Common Sources](#common-sources "Jump To Section")

* [DOM-XSS Sinks](#dom-xss-sinks "Jump To Section")

* [Open-Redirection Sinks](#open-redirection-sinks "Jump To Section")

* [Cookie Manipulation Sink](#cookie-manipulation-sink "Jump To Section")

* [JavaScript Injection Sinks](#javascript-injection-sinks "Jump To Section")

* [Document-Domain Manipulation Sink](#document-domain-manipulation-sink "Jump To Section")

* [WebSocket URL Poisoning Sink](#websocket-url-poisoning-sink "Jump To Section")

* [Link Manipulation Sinks](#link-manipulation-sinks "Jump To Section")

* [AJAX Request Header Manipulation Sinks](#ajax-request-header-manipulation-sinks "Jump To Section")

* [Local File-Path Manipulation Sinks](#local-file-path-manipulation-sinks "Jump To Section")

* [Client-Side SQL Injection Sink](#client-side-sql-injection-sink "Jump To Section")

* [HTML5 Storage Manipulation Sinks](#html5-storage-manipulation-sinks "Jump To Section")

* [XPath Injection Sinks](#xpath-injection-sinks "Jump To Section")

* [Client-Side JSON Injection Sinks](#client-side-json-injection-sinks "Jump To Section")

---

## What Are Sources and Sinks?

PortSwigger Definition For Sources:

> A source is a JavaScript property that accepts data that is potentially attacker-controlled. An example of a source is the location.search property because it reads input from the query string, which is relatively simple for an attacker to control. Ultimately, any property that can be controlled by the attacker is a potential source. This includes the referring URL (exposed by the document.referrer string), the user's cookies (exposed by the document.cookie string), and web messages.

PortSwigger Definition For Sinks:

> A sink is a potentially dangerous JavaScript function or DOM object that can cause undesirable effects if attacker-controlled data is passed to it. For example, the eval() function is a sink because it processes the argument that is passed to it as JavaScript. An example of an HTML sink is document.body.innerHTML because it potentially allows an attacker to inject malicious HTML and execute arbitrary JavaScript.

[Back To Top](#sources-and-sinks-cheatsheet "Jump To Top")

---

## Common Sources

The following are typical sources that can be used to exploit a variety of taint-flow vulnerabilities:

* document.URL

* document.documentURI

* document.URLUnencoded

* document.baseURI

* location

* document.cookie

* document.referrer

* window.name

* history.pushState

* history.replaceState

* localStorage

* sessionStorage

* IndexedDB (mozIndexedDB, webkitIndexedDB, msIndexedDB)

* Database

**Information Source** - [Dom-Based Vulnerabilities Lesson On PortSwigger](https://portswigger.net/web-security/dom-based "Dom Based Vulnerabilities Lesson On PortSwigger").

[Back To Top](#sources-and-sinks-cheatsheet "Jump To Top")

---

## DOM-XSS Sinks

The following are some of the main sinks that can lead to DOM-XSS vulnerabilities:

* document.write()

* document.writeln()

* document.domain

* element.innerHTML

* element.outerHTML

* element.insertAdjacentHTML

* element.onevent

The following jQuery functions are also sinks that can lead to DOM-XSS vulnerabilities:

* add()

* after()

* append()

* animate()

* insertAfter()

* insertBefore()

* before()

* html()

* prepend()

* replaceAll()

* replaceWith()

* wrap()

* wrapInner()

* wrapAll()

* has()

* constructor()

* init()

* index()

* jQuery.parseHTML()

* $.parseHTML()

**Information Source** - [DOM-Based XSS Lesson On PortSwigger](https://portswigger.net/web-security/cross-site-scripting/dom-based "DOM-Based XSS Lesson On PortSwigger")

[Back To Top](#sources-and-sinks-cheatsheet "Jump To Top")

---

## Open-Redirection Sinks

The following are some of the main sinks that can lead to DOM-based open-redirection vulnerabilities:

* location

* location.host

* location.hostname

* location.href

* location.pathname

* location.search

* location.protocol

* location.assign()

* location.replace()

* open()

* element.srcdoc

* XMLHttpRequest.open()

* XMLHttpRequest.send()

* jQuery.ajax()

* $.ajax()

**Information Source** - [DOM-Based Open-Redirection Lesson On PortSwigger](https://portswigger.net/web-security/dom-based/open-redirection "DOM-Based Open-Redirection Lesson On PortSwigger")

[Back To Top](#sources-and-sinks-cheatsheet "Jump To Top")

---

## Cookie Manipulation Sink

The following sink can lead to DOM-based cookie-manipulation vulnerabilities.

* document.cookie

**Information Source** - [DOM-Based Cookie Manipulation  Lesson On PortSwigger](https://portswigger.net/web-security/dom-based/cookie-manipulation "DOM-Based Cookie Manipulation  Lesson On PortSwigger")

[Back To Top](#sources-and-sinks-cheatsheet "Jump To Top")

---

## JavaScript Injection Sinks

The following are some of the main sinks that can lead to DOM-based JavaScript-injection vulnerabilities:

* eval()

* Function()

* setTimeout()

* setInterval()

* setImmediate()

* execCommand()

* execScript()

* msSetImmediate()

* range.createContextualFragment()

* crypto.generateCRMFRequest()

**Information Source** - [DOM-Based JavaScript Injection Sinks Lesson On PortSwigger](https://portswigger.net/web-security/dom-based/javascript-injection "DOM-Based JavaScript Injection Sinks Lesson On PortSwigger")

[Back To Top](#sources-and-sinks-cheatsheet "Jump To Top")

---

## Document-Domain Manipulation Sink

The following sink can lead to DOM-based document-domain manipulation vulnerabilities.

* document.domain

**Information Source** - [DOM-Based Document-Domain Manipulation Sink Lesson On PortSwigger](https://portswigger.net/web-security/dom-based/document-domain-manipulation "DOM-Based Document-Domain Manipulation Sink Lesson On PortSwigger")

[Back To Top](#sources-and-sinks-cheatsheet "Jump To Top")

---

## WebSocket-URL Poisoning Sink

The following constructor can lead to WebSocket-URL poisoning vulnerabilities.

* WebSocket

**Information Source** - [DOM-Based WebSocket URL Poisoning Sink Lesson On PortSwigger](https://portswigger.net/web-security/dom-based/websocket-url-poisoning "DOM-Based WebSocket URL Poisoning Sink Lesson On PortSwigger")

[Back To Top](#sources-and-sinks-cheatsheet "Jump To Top")

---

## Link Manipulation Sinks

The following are some of the main sinks that can lead to DOM-based link-manipulation vulnerabilities:

* element.href

* element.src

* element.action

**Information Source** - [DOM-Based Link Manipulation Sinks Lesson On PortSwigger](https://portswigger.net/web-security/dom-based/link-manipulation "DOM-Based Link Manipulation Sinks Lesson On PortSwigger")

[Back To Top](#sources-and-sinks-cheatsheet "Jump To Top")

---

## Ajax Request-Header Manipulation Sinks

The following are some of the main sinks that can lead to DOM-based Ajax request-header vulnerabilities:

* XMLHttpRequest.setRequestHeader()

* XMLHttpRequest.open()

* XMLHttpRequest.send()

* jQuery.globalEval()

* $.globalEval()

**Information Source** - [DOM-Based AJAX Request Header Manipulation Sinks Lesson On PortSwigger](https://portswigger.net/web-security/dom-based/ajax-request-header-manipulation "DOM-Based AJAX Request Header Manipulation Sinks Lesson On PortSwigger")

[Back To Top](#sources-and-sinks-cheatsheet "Jump To Top")

---

## Local File-Path Manipulation Sinks

The following are some of the main sinks that can lead to DOM-based local file path manipulation vulnerabilities:

* FileReader.readAsArrayBuffer()

* FileReader.readAsBinaryString()

* FileReader.readAsDataURL()

* FileReader.readAsText()

* FileReader.readAsFile()

* FileReader.root.getFile()

**Information Source** - [DOM-Based Local File Path Manipulation Sinks Lesson On PortSwigger](https://portswigger.net/web-security/dom-based/local-file-path-manipulation "DOM-Based Local File Path Manipulation Sinks Lesson On PortSwigger")

[Back To Top](#sources-and-sinks-cheatsheet "Jump To Top")

---

## Client-Side SQL-Injection Sink

The following JavaScript database function can lead to client-side SQL-injection vulnerabilities.

* executeSql()

**Information Source** - [DOM-Based Client-Side SQL Injection Sink Lesson On PortSwigger](https://portswigger.net/web-security/dom-based/client-side-sql-injection "DOM-Based Client-Side SQL Injection Sink Lesson On PortSwigger")

[Back To Top](#sources-and-sinks-cheatsheet "Jump To Top")

---

## HTML5 Storage Manipulation Sinks

The following are some of the main sinks that can lead to DOM-based HTML5-storage manipulation vulnerabilities:

* sessionStorage.setItem()

* localStorage.setItem()

**Information Source** - [DOM-Based HTML5 Storage Manipulation Sinks Lesson On PortSwigger](https://portswigger.net/web-security/dom-based/html5-storage-manipulation "DOM-Based HTML5 Storage Manipulation Sinks Lesson On PortSwigger")

[Back To Top](#sources-and-sinks-cheatsheet "Jump To Top")

---

## XPath Injection Sinks

The following are some of the main sinks that can lead to DOM-based XPath-injection vulnerabilities:

* document.evaluate()

* element.evaluate()

**Information Source** - [DOM-Based Client-Side XPath Injection Sinks Lesson On PortSwigger](https://portswigger.net/web-security/dom-based/client-side-xpath-injection "DOM-Based Client-Side XPath Injection Sinks Lesson On PortSwigger")

[Back To Top](#sources-and-sinks-cheatsheet "Jump To Top")

---

## Client-Side JSON Injection Sinks

The following are some of the main sinks that can lead to DOM-based client-side JSON injection vulnerabilities:

* JSON.parse()

* jQuery.parseJSON()

* $.parseJSON()

**Information Source** - [DOM-Based Client-Side JSON Injection Sinks Lesson On PortSwigger](https://portswigger.net/web-security/dom-based/client-side-json-injection "DOM-Based Client-Side JSON Injection Sinks Lesson On PortSwigger")

[Back To Top](#sources-and-sinks-cheatsheet "Jump To Top")

---

