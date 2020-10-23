# Introductory HTML and JavaScript

---

## How People Access the Web

Most people access websites using software called **web browsers**.

- Firefox
- Internet Explorer
- Safari
- Chrome
- Opera

Some people who are visually impaired use programs called **screen readers** to access websites. These programs read out the contents of a computer screen to the user.

People access websites on an increasing number of devices including, but not limited to:

- desktop computers
- laptops
- tablets
- mobile phones

### Web Servers

Web servers are specialized computers that host websites. They are optimized to send out web pages and are constantly connected to the internet. They are most commonly maintained by **web hosting** companies.

## Websites

All websites use **HTML** _(HyperText Markup Language)_ and **CSS** _(Cascading Style Sheets)_. Many websites also incorporate **JavaScript** to give them functionality or make them dynamic. Content management systems, blogging software and e-commerce platforms routinely make use of additional elements/technologies in their websites.

All websites have a unique **IP address** associated with them and the server they are located on. **Domain Name System** (DNS) servers are repositories for all of these addresses and they function similarly to phone book listings to direct browsers to the correct location of the website..

## Structure

HTML is the language which describes and gives web pages structure. It is made up of characters called HTML **elements** inside of angled brackets called **tags**. These usually come in pairs: an opening and a closing tag. Each element tells the browser something about the structure of the information contained within. Tags act like containers for the text or other information located inside of them.

```HTML
<h1>This would be a heading</h1>
```

would indicate to the browser to display:

# This would be a heading

on the web page.

`<h1>` is the **opening tag**

`</h1>` is the **closing tag**

Most elements can have one or more **attributes** such as _class_ or _id_ which provide additional information about their contents. Attributes consist of two parts: a **name** and a **value** separated by an `=` sign. for instance:

```HTML
<p lang="en-us">Paragraph in English</p>
```

### Basic HTML Structure of a Web Page

```HTML
<!DOCTYPE html>
  <html>
    <head>
      <title>The Title of the Page</title>
    </head>
    <body>
      <h1>A Heading in the Body of the Page</h1>
      <p>Anything in the body is displayed in the main browser window</p>
    </body>
  </html>
```

- `<body>` Everything inside this element is shown in the main browser window.
- `<head>` Located before the `<body>` element, this element contains information _about_ the page.
- `<title>` The content of this element is displayed at the top of the browser or on the 'tab' above the address bar. The `<title>` element is usually located within the `<head>` element of the page.

- `<!DOCTYPE html>` Each webpage should begin with a declaration such as this, which tells the browser the version of HTML the page is using.

##### To learn HTML, you need to know what tags are available for you to use, what they do, and where they can go.

## Extra Markup

- DOCTYPES tell browsers which version of HTML is being used
- Comments can be added to code to make it easier to understand. They are not displayed on the web page and are structured as follows:

```HTML
<-- Comment Here -->
```

- The **id** and **class** attributes are used to identify or group specific elements
- `<div>` and `<span>` elements allow us to group block-level and inline elements together, respectively
- `<iframes>` allow other web pages to be shown through windows "cut out"" of the web page
- The `<meta>` tag is an **open tag** located in the `<head>` tag and contains information about the web page. It is not visible to users but can convey information about the page to search engines, who created the page, or if the page is time-sensitive
- **Escape characters** are used to include special charcters in web pages. Some examples are:

| **Character** | **CODE**   | **Description**        |
| ------------- | ---------- | ---------------------- |
| &lt;          | `&lt;`     | _Less-than sign_       |
| &gt;          | `&gt;`     | _Greater-than sign_    |
| &amp;         | `&amp;`    | _Ampersand_            |
| &quot;        | `&quot;`   | _Quotation Mark_       |
| &copy;        | `&copy;`   | _Copyright symbol_     |
| &reg;         | `&reg;`    | _Registered trademark_ |
| &trade;       | `&trade;`  | _Trademark_            |
| &divide;      | `&divide;` | _Division sign_        |
