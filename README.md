# Browser render process of HTML, CSS, JS to DOM

## 1. Abstract
The purpose of this article is to explain, in very simple terms, the steps your browser takes to convert HTML, CSS and JavaScript into a working website you can interact with.

Knowing the process your browser takes to bring websites to life will empower you to optimize your web applications for faster speed and performance. 
The process need to be followed is shown in below fig.

![GitHub Dark](https://blog.logrocket.com/wp-content/uploads/2021/06/how-browser-rendering-works.png) 


## [**2. Introduction**](#21-what-is-browser-rendering)
## 2.1 What is browser rendering?

`Browser rendering` is a process in which a web browser interprets and displays HTML and CSS code in its viewport. A web browser has a rendering engine and these engines can have slightly different ways in interpreting HTML and CSS, which can lead to inconsistencies in the look of a site. The widespread adoption of HTML 5 and tests such as Acid3 have improved general compatibility in modern browsers. Browser rendering is also known as a `browser engine`. . Browser rendering converts the data of `HTML`, `CSS`, and `JS` to `DOM` and `CSSOM`.

![GitHub dark](https://developers.google.com/web/fundamentals/performance/rendering/images/intro/frame-full.jpg) 

## 2.2 what is DOM?

DOM stands for `Document Object Model`. It is a programming interface that allows us to `create`, `change`, or `remove` elements from the document. We can also add events to these elements to make our page more dynamic.

The DOM views an HTML document as a `tree of nodes`. A node represents an HTML element. 

![GitHub Dark](https://www.freecodecamp.org/news/content/images/size/w1000/2021/09/Document.jpg)


There are a few different methods for selecting an element in the HTML document.
In this article, we will focus on three of those methods:

    *getElementById()
    *querySelector()
    *querySelectorAll()

getElementById()

In HTML, ids are used as unique identifiers for the HTML elements. This means you cannot have the same id name for two different elements. 

 ## **3. The mechanism behind browser rendering process:**

 While the browser receives the raw bytes of data and kicks off the DOM construction process, it will also make a request to fetch the main.css stylesheet linked. As soon the browser begins to parse the HTML, upon finding a link tag to a CSS file, it simultaneously makes a request to fetch that.

In other words, the raw bytes of data are converted to characters, then tokenized. Nodes are also formed, and, finally, a tree structure is formed.

What is a tree structure? Well, most people know there’s something called the DOM. In the same way, there’s also a CSS tree structure called the CSS Object Model (CSSOM).

You see, the browser can’t work with either raw bytes of HTML or CSS. This has to be converted to a form it recognizes — and that happens to be these tree structures.

Most commonly, that involves parsing HTML (the language that describes the structure of web pages) and CSS (the language that describes how HTML should be 
styled), and then rendering the web page the HTML & CSS describes.

![GitHub Dark](https://res.cloudinary.com/practicaldev/image/fetch/s--CPYIXBSH--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://cdn-images-1.medium.com/proxy/1%2AIb2Ufggiy67xg02Jp8CYhQ.png)
![Data reading from files](https://res.cloudinary.com/practicaldev/image/fetch/s--lbir5Xqh--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://cdn-images-1.medium.com/max/1024/1%2AVmD21Exnic6eQxj5xGrA-Q.png)

***steps***

* The raw bytes of data is not understandable for the browser.
  So the browser needs to work with DOM.
* Then it converts the `raw bytes` of data into `characters` and these `characters` are again converted into `tokens`.
* Then  these `tokens` are converted the start tags and end tags into `nodes`.
* `Nodes` are linked to a tree-like structure known as `DOM`, which is the Javascript representation of HTML, Simultaneously by following this process web browser converts CSS code to `CSSOM`. 
* After the browser created the DOM and CSSOM it creates a tree known as `Render tree`. The render tree only consists of nodes that are visible on the screen. If the node is marked as none then it won't be a part of the Render Tree.

![DOM](https://res.cloudinary.com/practicaldev/image/fetch/s--wYwH6uKq--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://cdn-images-1.medium.com/proxy/1%2A10ytkQcfKdbfGQxvYj2-5A.png)




**Render Tree**


The DOM contains all the information about the page’s HTML element’s relationships, while the CSSOM contains information on how the elements are styled.

Okay, the browser now combines the DOM and CSSOM trees into something called a render tree.
The render tree contains information on all visible DOM content on the page, and all the required CSSOM information for the different nodes.
Note that if an element as been hidden by CSS e.g. by using display; none, the node will not be represented in the render tree.
The hidden element will be present in the DOM but not the render tree.
The reason being the render tree combines information from both the DOM and the CSSOM, so it knows not to include a hidden element in the tree.
With the render tree constructed, the browser moves on to the next step, layout!


![Render Tree](https://miro.medium.com/max/1400/1*-ffAB0BPwrt-AQHIea4kWQ.png)

 ## ***4. References***
[Render-tree Construction, Layout, and Paint by Ilya Grigorik](https://medium.com/weekly-webtips/understand-dom-cssom-render-tree-layout-and-painting-9f002f43d1aa)

[browser-rendering](https://dev.to/bnevilleoneill/how-browser-rendering-works-behind-the-scenes-1ce5)
