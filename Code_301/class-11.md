# EJS
---
## EJS

**EJS** is a templeting language or engine that we can use to generate HTML with plain JavaScript. EJS stands for Embedded JavaScript. It is most useful when we have to output when we are dealing with real-time updates or generating dynamic contents.

Even though there are a number of options to use for these kinds of processes, EJS is popular because it is relatively esy to set up and its syntax and logic is simple.

The following examples, from *Linda Ikechukwu's* article, [*"Using EJS as a Template Engine in your Express App"*](https://medium.com/@Linda_Ikechukwu/https-medium-com-linda-ikechukwu-using-ejs-as-a-template-engine-in-your-express-app-cb3d82c15e17). The second block shows what the first block might look like when utilizing EJS:

```JavaScript
var html = "<h1>"+data.title+"</h1>"
html += "<ul>"
for(var i=0; i<data.supplies.length; i++) {
    html += "<li><a href='supplies/"+data.supplies[i]+"'>"
    html += data.supplies[i]+"</a></li>"
}
html += "</ul>"
```

```
<h1><%=title%></h1>
<ul>
   <%for (var i=0;i<supplies.length; i++){%>
     <li>
         <a href='supplies/<%= supplies[i] %>'></a>
         <%=supplies[i]%>
     </li>
   <%}%>
</ul>
```

To use EJS, we must first install it in our project folder as follows:

```
npm install ejs --save
```

### Intro to EJS

The following notes were drawn from the video series [*"Intro to EJS in ExpressJS"*](https://www.youtube.com/playlist?list=PL7sCSgsRZ-slYARh3YJIqPGZqtGVqZRGt) by *WalkThroughCode*.

#### Getting Started

After installing ejs in our project folder we need to create a folder named *views* and a file named *index.ejs*.

In our server.js we need to add lines to `require('body-parser');` and `require('path');` We also ne to add the following code:
- `app.use('body-parser');`
- `app.set('views', path.join(_dirname, 'views'));`
- `app.set('view engine', 'ejs');`
- `app.get('/', function(req,res) {res.render('index');
});`
- `app.listen(8000, function() { console.log('heard on 8000');
});`

#### Injecting and Evaulating Variables

Variables can be inserted into EJS templates and evaluated as well. to evaluate the variables we must remember to include the `=` character in the EJS tags. For instance:
```
<%= foo %>
```

#### For Loops and Arrays

We can use a line in our server.js to loop through arrays in out EJS template file to generate viewable content:
```JavaScript
res.render('index', { people: [ {name: bob}, {name: sam}]});
```

...and, inside our index.ejs, we include this code:
```html
<ul>
  <% for(var person of people) { %>
  <li><%= person.name %></li>
  <% } %>
```

[Back to Main](../README.md)
