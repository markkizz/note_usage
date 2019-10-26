# DOM manipulate
---------------
## Element Selector
* document.getElementById()
* document.getElementsByClassName()
* document.getElementsByTagName()
* document.querySelector()
* document.querySelectorAll()

```
//finds element by id
document.getElementById(id)
```
```
//you can select any index that you want by
document.getElementById(id)[0]
```
```
//finds elements by class name
document.getElementsByClassName(name)
```
```
//finds elements by tag name
document.getElementsByTagName(name)
>>>h1, div, ul, li, a


//e.g.
var el = document.getElementByid("demo")
>>> <div id="demo">...</div>
```
```
find the first element by css name
document.querySelector() //e.g (.class), (#id)
```
```
select all of element
document.querySelectorAll()
```

the method of element selector are return collection of all elements in the document or return as an Array
```
<p>hi</p>
<p>hello</p>
<p>hi</p>
<script>
var arr = document.getElementsByTagName("p");
for (var x = 0; x < arr.length; x++) {
    arr[x].innerHTML = "Hi there";
}
</script>


>>>
<p>Hi there</p>
<p>Hi there</p>
<p>Hi there</p>
.innerHTML = use for change a content in document
```

### Text and content manipulate
* textContent  - return only string
* innerHTML - return whole the element
`>>  <p>...</p>`

### - Changing Attributes
* changing style using js - `.classList()`
* changing  attributes in html - `setAttribute()`

### - Change src
```
<img id="myimg" src="orange.png" alt="" />
<script>
    var el = document.getElementById("myimg");
    el.src = "apple.png";
</script>


// or using .getAttribute() for changing
var el = document.getElementById("myimg");
el.setAttribute("img", "apple.png")
```

### - Change href
```
<a href="http://www.example.com">Some link</a>
<script>
    var el = document.getElementsByTagName("a");
    el[0].href = "http://www.sololearn.com";
</script>
```

### - Change Style
It change style in css `.style.anyInCss` {backgroud, width, height, etc}
```
<div id="demo" style="width:200px">some text</div>
<script>
    var x = document.getElementById("demo");
    x.style.color = "6600FF";
    x.style.width = "100px";
</script>
```

## ClassList
- A read-only list that contains the classes for given element.  Not an array!!
```
/*DEFINE A CLASS IN CSS*/
.another-class {
    color: purple;
    fontSize: 76px;
}
AND
var tag = document.querySelector("h1");

//ADD A CLASS TO THE SELECTED ELEMENT
tag.classList.add("another-class");

//REMOVE A CLASS
tag.classList.remove("another-class");

//*__TOGGLE A CLASS - like a click on-off additional css style__
tag.classList.toggle("another-class");
```
## ----------------------- Recommend Technique------------------------
### Rather than directly manipulating style with JS, we can define a CSS class and then toggle it on/off with JS
```
/*DEFINE A CLASS IN CSS*/
.some-class {
  color: blue;
  border: 10px solid red;
}
AND
//In script file//
var tag = document.getElementById("highlight");
//ADD THE NEW CLASS TO THE SELECTED ELEMENT
tag.classList.add("some-class");
//or use .toggle to on/off
```
------------------------------------------------------//------------------------------------------------------
### Adding & Removing Element

### Creating Elements
* element.cloneNode()  - clones an element and returns the resulting node.
* document.createElement(element)   - creates a new element node.
* document.createTextNode(text)  - creates a new text node.

### Animation

- Interval
```
//using setInterval() method
var t = setInterval(fn(),1000)   //1000 in ms == 1 sec


//to stop interval using clearInterval()
    function move() {
        if(pos >= 150) {
            clearInterval(t);
        }
        else {
            pos += 1;
            box.style.left = pos+"px";
        }
    }
```

## __Event common use__
* An event occurs when user interact with element or children

| Event  | Description  |
|--------|--------------|
|.onclick|occurs when the user clicks on an element|
|.onchange  |occurs when the content of `<input>`, `<keygen>`, `<select>` and `<textarea>` have change  |
|.onmouseover |oc when the pointer is moved onto an element or one of it children|
|.onmouseout|   |




## ------------------------------More Over-----------------------------
### Family of DOM
* element.childNodes  - returns an array of an element's child nodes.
* element.firstChild  - returns the first child node of an element.
* element.lastChild   - returns the last child node of an element.
* element.hasChildNodes  - returns true if an element has any child nodes, otherwise false.
* element.nextSibling  -  returns the next node at the same tree level.
* element.previousSibling  - returns the previous node at the same tree level.
* element.parentNode  - returns the parent node of an element.
```
<html>
  <body>
    <div id ="demo">
      <p>some text</p>
      <p>some other text</p>
    </div>
    <script>
     var a = document.getElementById("demo");
     var arr = a.childNodes;
     for(var x=0;x<arr.length;x++) {
       arr[x].innerHTML = "new text";
     }
    </script>
  </body>
</html>
>>>
new text

new text
(include white space or break)
```
