minimal web browser in rust
========
I worked on creating a minimal browser in Rust as a way to better understand what happens behind the scences of web applications and more specifically how web browsers handle and respond to requests using TCP and HTTP protocols and then render those requests and display information.

The current features of this project include:

1. Basic web server functionality: Implemented HTTP protocol in Rust. This establishes and listens to a TCP connection and then reads data from the TCP stream. It also recieves an HTTP request, validates the request, and then sends the relevant HTMl files as a response.
Better, more human readable text rendering: Split lines at word boundaries and enable text styling and sizing.
2. HTML parser: Parses the HTML source code and transform it into a tree of DOM nodes. As HTML has its own parsing algorithm, its was necessary to handle and recognize attributes of the various HTML elements. In specific as the the HTML parsing algorithm does not reject invalid input, the parser must provide sane automatic fixes if some HTML tokens are incorrect. After such rectifications, the parser must recursively build up and comb through the entire tree of DOM nodes.
3. Inline layout: Using the recusrive HTML parsing algorithm, the HTML elements are converted to produce a tree to deomonstrate how the text will be laid out on screen. To make the text easy to easy to read and digest,each HTML tag has characteristic layout features of size and position when displayed. On top of this, additional formatting is applied to make rendered text easier to identify.
4. CSS Parser: Constructed a seperate style sheet for the browser with attributes for other CSS files as well as providing inline layout features for HTML tags. The parser ultimately builds final layout structure of how text appears on the screen, and parses the code so that it fits these limitations.