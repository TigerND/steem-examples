### How to embed images directly to your HTML or Markdown

![Img](https://i.imgsafe.org/82dac99.jpg)

When you code a web page, you’ll oftentimes want to include images. In almost every case you’ll throw down a line of code that looks something like this:

```html
<img src="location/of/image.png" alt="alternative text" scale="0">
```

But did you know that you can embed your image directly into the HTML without having to link to an external file? Yep, but first, why would you want to? In a word, portability. In certain cases, you may want to be able to pick up your page and simply relocate it without worrying about whether linked images are going to transfer correctly as well. How do we do this? Observe.

Let’s say you have an image that you want to include in your markup — when you link to it, the browser interprets it as encoded data in a format dictated by your  tag. In theory, you can convert the image directly to encoded data and put it directly into the src parameter, right? Let’s find out.

__You can use Base64 code instead of an image location.__

```html
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAIAAAD8GO2jAAAACXBIWXMAAAsTAAALEwEAmpwYAAAA
B3RJTUUH4AccEA4yOA1aawAAAyFJREFUSMftlltIFGEUx8/3zTd7cS/tels1TbeyqLSiorKUIExI
KEMiIiiMopcgCLKH6KGg6AI9+aARVPRQVPZgUQ8pBElJZZRlpIVlZuiqm7q3mZ3Ld3roQtgyzYZS
D/0H5mH4vvnNOXPO/3wEEWEqRWGK9Q8A8PvtVrfc2hcHAFVTJxPAOd90+CYAP/dMjyoAAJuP3JlM
QF8g9LBzSNEwx0ludOkA2Nz+aSwqTRrAn+0pKfLVNrRWzWNvRuDDuL6hJH/PmXtmQ0ATetETSN3Y
EBwPbbke3toY7vk04q6sj6uKmb2mqqjInyFQISLhvhXiYJTm5aQVz0xVVD5pEYyGpc73AUTsHFJO
tEYQsfF+F5oTSaqTP0txr91CgJjfwhI+HQtHX/UGKZn4IvKtLSZqZrbHl+ZKAtDR/bH8UIuNAQUd
AHQiGn9m3d7SnZULkwBYLRa7RfDPKchesY7xeNvl84JoNQAEQ7GorDpsotk+cNpFRBRFxjU1EugH
yowjOHm1o3D7xR3HmswC0j0OACJJMgDIcY38zqz2VxfNzXHcbh88fumBKUBWupcSHpdVAKCE/9YO
S4tzrx2tsjDacOulOasgxOO0KlIMEFMcTuNS5oipbjujhFIyPC6Z9SKfN0WOhAWuWJxuRG7cqjMy
Xf3DIU3nSwozzQL8PieC0NfWQl1pDpvRT2aU7Dp9t7y2KRxTTu0pNQuoWu1XND40GIwF+t1ZuQYA
Tdc73o2sWuB7XFddtih/YrIN8jt9c73KBZHB7KXLXj9qT7gmxUp7r+z+w3lw4WAFAKgadD95mnCB
ovGa8sI/HzgVy2fVrM3TdOQ8cZTVK7OP7FpjDEicolAkuu1oU/PzgA6iwyYQ+Hr9fAwARJQUrmty
2fyMswfWz83PSALwQ4Hhkb4hKTAaHo8qclzRqZWiYmNsmoNlpLpz0+25WZm/li38ZMOEc05IEv4O
AFEV3wTBa0cCIGtgYzAQBr8XUgR8+2GAMYFzPhqSyhYXMIGRb3MnGYbGYUxGjQOjIAqg6GChIFAA
IKocU3Vut4iKpntcNoFS8v9s+tcBXwDEIPHZH2+GUwAAAABJRU5ErkJggg" alt="beastie.png" scale="0">
```

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAIAAAD8GO2jAAAACXBIWXMAAAsTAAALEwEAmpwYAAAA
B3RJTUUH4AccEA4yOA1aawAAAyFJREFUSMftlltIFGEUx8/3zTd7cS/tels1TbeyqLSiorKUIExI
KEMiIiiMopcgCLKH6KGg6AI9+aARVPRQVPZgUQ8pBElJZZRlpIVlZuiqm7q3mZ3Ld3roQtgyzYZS
D/0H5mH4vvnNOXPO/3wEEWEqRWGK9Q8A8PvtVrfc2hcHAFVTJxPAOd90+CYAP/dMjyoAAJuP3JlM
QF8g9LBzSNEwx0ludOkA2Nz+aSwqTRrAn+0pKfLVNrRWzWNvRuDDuL6hJH/PmXtmQ0ATetETSN3Y
EBwPbbke3toY7vk04q6sj6uKmb2mqqjInyFQISLhvhXiYJTm5aQVz0xVVD5pEYyGpc73AUTsHFJO
tEYQsfF+F5oTSaqTP0txr91CgJjfwhI+HQtHX/UGKZn4IvKtLSZqZrbHl+ZKAtDR/bH8UIuNAQUd
AHQiGn9m3d7SnZULkwBYLRa7RfDPKchesY7xeNvl84JoNQAEQ7GorDpsotk+cNpFRBRFxjU1EugH
yowjOHm1o3D7xR3HmswC0j0OACJJMgDIcY38zqz2VxfNzXHcbh88fumBKUBWupcSHpdVAKCE/9YO
S4tzrx2tsjDacOulOasgxOO0KlIMEFMcTuNS5oipbjujhFIyPC6Z9SKfN0WOhAWuWJxuRG7cqjMy
Xf3DIU3nSwozzQL8PieC0NfWQl1pDpvRT2aU7Dp9t7y2KRxTTu0pNQuoWu1XND40GIwF+t1ZuQYA
Tdc73o2sWuB7XFddtih/YrIN8jt9c73KBZHB7KXLXj9qT7gmxUp7r+z+w3lw4WAFAKgadD95mnCB
ovGa8sI/HzgVy2fVrM3TdOQ8cZTVK7OP7FpjDEicolAkuu1oU/PzgA6iwyYQ+Hr9fAwARJQUrmty
2fyMswfWz83PSALwQ4Hhkb4hKTAaHo8qclzRqZWiYmNsmoNlpLpz0+25WZm/li38ZMOEc05IEv4O
AFEV3wTBa0cCIGtgYzAQBr8XUgR8+2GAMYFzPhqSyhYXMIGRb3MnGYbGYUxGjQOjIAqg6GChIFAA
IKocU3Vut4iKpntcNoFS8v9s+tcBXwDEIPHZH2+GUwAAAABJRU5ErkJggg" alt="beastie.png">

<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZlcnNpb249IjEuMSI+CiAg
PHNjcmlwdCB0eXBlPSJhcHBsaWNhdGlvbi9lY21hc2NyaXB0Ij4gPCFbQ0RBVEFbCiAgICBhbGVy
dCgnaGVsbG8gdGhlcmUnKQogIF1dPiA8L3NjcmlwdD4KICA8Y2lyY2xlIGN4PSI1MCIgY3k9IjUw
IiByPSI0MCIgZmlsbD0icmVkIiBzdHJva2U9ImJsYWNrIi8+Cjwvc3ZnPg" alt="hello.svg">

It's a pity that [steemit.com](https://stemmin.com) can't handle it correctly :(

__Would be nice to have it working properly__

![Pic](https://s31.postimg.org/l3wzs912j/Screenshot_2016_07_28_19_39_25.png)
