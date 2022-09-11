minimal web browser in rust
========
I worked on creating a minimal browser in Rust as a way to better understand what happens behind the scenes of web applications and more specifically how web browsers handle and respond to requests using TCP and HTTP protocols and then render those requests and display information.

The current features of this project include:

Basic web server functionality: Implemented HTTP protocol in Rust. This establishes and listens to a TCP connection and then reads data from the TCP stream. It also receives an HTTP request, validates the request, and then sends the relevant HTML files as a response.

HTML parser: Parses the HTML source code and transforms it into a tree of DOM nodes. As HTML has its own parsing algorithm, it was necessary to handle and recognize the attributes of the various HTML elements. In specific as the HTML parsing algorithm does not reject invalid input, the parser must provide sane automatic fixes if some HTML tokens are incorrect. After such rectifications, the parser must recursively build up and comb through the entire tree of DOM nodes.

Block layout: Using the recursive HTML parsing algorithm, the HTML elements are converted to produce a tree to demonstrate how the text will be laid out on screen. To make the text easy to read and digest, each HTML tag has characteristic layout features of size and position when displayed. On top of this, additional formatting is applied to make the rendered text easier to identify.

CSS Parser: Constructed a separate style sheet for the browser with attributes for other CSS files as well as providing inline layout features for HTML tags. The parser ultimately builds the final layout structure of how text appears on the screen, and parses the code so that it fits these limitations.
