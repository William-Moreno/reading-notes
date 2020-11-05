# Forms and Events

---

## Forms

> The best known _form_ on the web is probably the search box that sits right in the middle of Google's homepage.

Forms are used for many other things besides conducting a search, however. Some of them are:

- registering for memberships
- shopping online
- signing up for newsletters and mailing lists

There are several types of form controls that you can use to collect information from site visitors:

- Adding Text
  - **Text Input _(single-line)_** - Used for a single line of text such as an email address or name
  - **Password Input** - Like a single line text box, but it masks the characters entered
  - **Text Area _(multi-lines)_** - For longer text entries like messages or comments
- Making Choices
  - **Radio Buttons** - For use when a user must select one of a number of options
  - **Checkboxes** - When a user can select and unselect one or more options
  - **Drop-down Boxes** - When a user must pick one of a number of options from a list
- Submitting Forms
  - **Submit Buttons** - To submit data from your form to another web page
  - **Image Buttons** - Similar to submit buttons but they allow you to use an image
- Uploading Files
  - **File Upload** - Allows users to upload files to a website

### How Forms Work

A User fills in a form and then presses a button to submit the information to the server. The name of each form control is sent to the server along with the value the user entered. The server processes the information using a programming language. THe server creates a new page to send back to the browser based on the information received.

A form may have several form controls. The server needs to know which piece of inputted data corresponds with which form element. For example:

```HTML
username=Ivy
```

### Form Structure

We create forms in HTML with the `<form>` element. This tag always carries an `action` attribute (which is the url of the page that will receive the information from the form) and a `method`, which will be either `"get"` or `"post"`. by default this value is "get".

#### Text Input

We create this with the `<input>` element with the attributes - `type="text"`, `name`, and `maxlength `

#### Password Input

This is similar to above, however, our `<input>` can have `type="password"` instead

#### Text Area

Created with `<textarea>`

#### Radio Button

`<input>` with `type="radio"` can have `name`, `value` and `checked` attributes _("checked" can cause a choice to be already selected when the page loads)_

#### Checkbox

`<input>` with `type="checkbox"` can have `name`, `value` and `checked` attributes _(the same as radio button)_

#### Drop Down List Box

The `<select>` element is used to create a drop down
list box containing two or more `<option>` elements. the `<name>` attribute indicates the form control being sent to the server

#### Multiple Select Box

The `<select>` element can turn a drop down box into a mutli-selection tool using the `<size>` and `<multiple>` attributes
