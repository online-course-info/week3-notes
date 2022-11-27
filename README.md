# Week 3 - Forms

This lesson will be **HARD**

>An HTML form is used to collect user input. The user input is most often sent to a server for processing

# The `<form>` element

>HTML `<form>` element **is used** to create an HTML form for user input:

The code example:

```html
<form>
    //form elements
</form>
```

# The `<input>` Element

>The HTML `<input>` element is the most used form element.

>An `<input>` element can be displayed in many ways, depending on the `type` attribute

Here is some examples:

![image](https://user-images.githubusercontent.com/119107805/204123979-88cccc09-6851-41fe-b341-6e9311f58d11.png)

# Text Fields

>The `<input type="text">` **defines** a _single-line_ input field for text input

```html
  <form>
    <label for="fname">First name:</label><br>
    <input type="text" id="fname" name="fname"><br>
    <label for="lname">Last name:</label><br>
    <input type="text" id="lname" name="lname">
  </form>
```

_Your output will be like this:_

![image](https://user-images.githubusercontent.com/119107805/204124027-597a5dc2-49d8-4481-b23c-83d04fb9fd6b.png)

# The `<label>` Element

>Notice the use of the `<label>` element in the example above

>The `<label>` tag **defines** _a label_ for many form elements

>The `<label>` element **is useful** for _screen-reader users_, because the screen-reader _will read_ out loud the label when the user focus on the `input` element

>The <label> element also help users who have difficulty clicking on very small regions (such as radio buttons or checkboxes) - because when the user clicks the text within the <label> element, it toggles the radio button/checkbox

>The for attribute of the <label> tag should be equal to the id attribute of the <input> element to bind them together

# Radio Buttons

>The `<input type="radio">` defines a radio button.

>Radio buttons let a user **select** _ONE_ of a limited number of choices.

This is code example:

```html
<p>Choose your favorite Web language:</p>
<form>
  <input type="radio" id="html" name="fav_language" value="HTML">
  <label for="html">HTML</label><br>
  <input type="radio" id="css" name="fav_language" value="CSS">
  <label for="css">CSS</label><br>
  <input type="radio" id="javascript" name="fav_language" value="JavaScript">
  <label for="javascript">JavaScript</label>
</form>
```

_Your output will be like this:_

![image](https://user-images.githubusercontent.com/119107805/204124170-2d2238bd-752b-482f-aed6-a94c05048bcf.png)

# Checkboxes

>The `<input type="checkbox">` **defines** a checkbox

>Checkboxes let a user select ZERO or MORE options of a limited number of choices

This is code example:

```html
<form>
  <input type="checkbox" id="vehicle1" name="vehicle1" value="Bike">
  <label for="vehicle1"> I have a bike</label><br>
  <input type="checkbox" id="vehicle2" name="vehicle2" value="Car">
  <label for="vehicle2"> I have a car</label><br>
  <input type="checkbox" id="vehicle3" name="vehicle3" value="Boat">
  <label for="vehicle3"> I have a boat</label>
</form>
```

_Your output will be like this:_

![image](https://user-images.githubusercontent.com/119107805/204124250-c11d4db6-6780-4313-a41c-cc0f55a614eb.png)

# The Submit Button

>The `<input type="submit">` defines a button for submitting the form data to a form-handler

>The form-handler **is typically** a _file on the server with a script_ for processing input data

>The `form-handler` **is specified** in the form's _action attribute_

The code example:

```html
<form action="/action_page.php">
  <label for="fname">First name:</label><br>
  <input type="text" id="fname" name="fname" value="John"><br>
  <label for="lname">Last name:</label><br>
  <input type="text" id="lname" name="lname" value="Doe"><br><br>
  <input type="submit" value="Submit">
</form>
```

_Your output will be like this:_

![image](https://user-images.githubusercontent.com/119107805/204124307-8bd1e73c-6f55-408b-81ac-7620a51c93cd.png)

# The Name Attribute for `<input>`

>Notice that each input field must have a `name` attribute to be submitted

>If the `name` attribute is omitted, the value of the input field will not be sent at all

This example will **not** _submit_ **the value** of the "First name" input field: 

```html
  <form action="/action_page.php">
    <label for="fname">First name:</label><br>
    <input type="text" id="fname" value="John"><br><br>
    <input type="submit" value="Submit">
  </form>
```

# HTML Form Attributes

>This chapter **describes** the different attributes for the HTML `<form>` element

# The Action Attribute

>The action attribute defines the action to be performed when the form is submitted

>Usually, the form data is sent to a file on the server when the user clicks on the submit button

>In the example below, the form data is sent to a file called "action_page.php". This file contains a server-side script that handles the form data

**Tip:** If the `action` attribute is omitted, the action is set to the current page

# The Target Attribute

>The `target` attribute specifies where to display the response that is received after submitting the form

>The `target` attribute can have one of the following values

![image](https://user-images.githubusercontent.com/119107805/204124489-5293d343-dfa8-4095-8be1-2ac0e27ed260.png)

>The default value is `_self` which means that the _response will **open** in the current window_

The code example:

```html
  <form action="/action_page.php" target="_blank">
      //your html code+
  </form>
```

# The Method Attribute

>The `method` attribute specifies the HTTP method to be used when submitting the form data

>The form-data can be sent as URL variables (with `method="get"`) or as HTTP post transaction (with `method="post"`)

>The default HTTP method when submitting form data is GET

Example with GET:

```html
  <form action="/action_page.php" method="get">
      //your html code
  </form>
```

Example with POST:

```html
    <form action="/action_page.php" method="post">
          //your html code
    </form>
```

**Notes on GET:**

>Appends the form data to the URL, in name/value pairs

>NEVER use GET to send sensitive data! (the submitted form data is visible in the URL!)

>The length of a URL is limited (2048 characters)

>Useful for form submissions where a user wants to bookmark the result

>GET is good for non-secure data, like query strings in Google

**Notes on POST:**

>Appends the form data inside the body of the HTTP request (the submitted form data is not shown in the URL)

>POST has no size limitations, and can be used to send large amounts of data

>Form submissions with POST cannot be bookmarked

# The Autocomplete Attribute

>The `autocomplete` attribute specifies whether a form should have autocomplete on or off

>When autocomplete is on, the browser automatically complete values based on values that the user has entered before

This is code example:

```html
  <form action="/action_page.php" autocomplete="on">
      //your html code
  </form>
```

# The Novalidate Attribute

>The `novalidate` attribute is a boolean attribute

>When present, it specifies that the form-data (input) should not be validated when submitted

# List of All `<form>` Attributes

![image](https://user-images.githubusercontent.com/119107805/204124798-a0e83a14-1cb8-4131-89fc-65de0d1f8a8e.png)

# The HTML `<form>` Elements

>The HTML `<form>` element can contain one or more of the following form elements:

>`<input>`

>`<label>`

>`<select>`

>`<textarea>`

>`<button>`

>`<fieldset>`

>`<legend>`

>`<datalist>`

>`<output>`

>`<option>`

>`<optgroup>`

# The `<input>` Element

>One of the most used form element is the `<input>` element

>The `<input>` element can be displayed in several ways, depending on the type attribute

This is a code example:

```html
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname">
```

# The `<label>` Element

The `<label>` element defines a label for several form elements.

The `<label>` element is useful for screen-reader users, because the screen-reader will read out loud the label when the user focus on the input element.

The `<label>` element also help users who have difficulty clicking on very small regions (such as radio buttons or checkboxes) - because when the user clicks the text within the `<label>` element, it toggles the radio button/checkbox.

The `for` attribute of the `<label>` tag should be equal to the `id` attribute of the `<input>` element to bind them together.

# The `<select>` Element

The `<select>` element defines a drop-down list

This is code example:

```html
  <label for="cars">Choose a car:</label>
  <select id="cars" name="cars">
    <option value="volvo">Volvo</option>
    <option value="saab">Saab</option>
    <option value="fiat">Fiat</option>
    <option value="audi">Audi</option>
  </select>
```

The `<option>` elements defines an option that can be selected

By default, the first item in the drop-down list is selected

To define a pre-selected option, add the `selected` attribute to the option

This is code example:

```html
  <option value="fiat" selected>Fiat</option>
```

# Visible Values

Use the `size` attribute to specify the number of visible values

This is code example:

```html
  <label for="cars">Choose a car:</label>
  <select id="cars" name="cars" size="3">
    <option value="volvo">Volvo</option>
    <option value="saab">Saab</option>
    <option value="fiat">Fiat</option>
    <option value="audi">Audi</option>
  </select>
```

# Allow Multiple Selections

Use the `multiple` attribute to allow the user to select more than one value

This is code example:

```html
  <label for="cars">Choose a car:</label>
  <select id="cars" name="cars" size="4" multiple>
    <option value="volvo">Volvo</option>
    <option value="saab">Saab</option>
    <option value="fiat">Fiat</option>
    <option value="audi">Audi</option>
  </select>
```

# The `<textarea>` Element

The `<textarea>` element defines a multi-line input field (a text area)

This is code example:

```html
  <textarea name="message" rows="10" cols="30">
  The cat was playing in the garden.
  </textarea>
```

_This will be your output:_

![image](https://user-images.githubusercontent.com/119107805/204125148-37bbfab3-266b-4991-a981-bb455d92abe6.png)

The `rows` attribute specifies the visible number of lines in a text area

The `cols` attribute specifies the visible width of a text area

# The `<button>` Element

The `<button>` element defines a clickable button

This is code example:

```html
  <button type="button" onclick="alert('Hello World!')">Click Me!</button>
```

_This will be your output:_

![image](https://user-images.githubusercontent.com/119107805/204125246-0757d9f7-3c9b-4922-bd85-ebab80b315b2.png)

**Note:** Always specify the type attribute for the button element. Different browsers may use different default types for the button element

# The `<fieldset>` and `<legend>` Elements

The `<fieldset>` element is used to group related data in a form

The `<legend>` element defines a caption for the `<fieldset>` element

This is code example:

```html
<form action="/action_page.php">
  <fieldset>
    <legend>Personalia:</legend>
    <label for="fname">First name:</label><br>
    <input type="text" id="fname" name="fname" value="John"><br>
    <label for="lname">Last name:</label><br>
    <input type="text" id="lname" name="lname" value="Doe"><br><br>
    <input type="submit" value="Submit">
  </fieldset>
</form>
```

_This will be your output:_

![image](https://user-images.githubusercontent.com/119107805/204125309-21424460-6bc7-44de-92d3-eae5cfd85728.png)

# The `<datalist>` Element

The `<datalist>` element specifies a list of pre-defined options for an `<input>` element

Users will see a drop-down list of the pre-defined options as they input data

The list attribute of the `<input>` element, must refer to the id attribute of the `<datalist>` element

This is code example:

```html
<form action="/action_page.php">
  <input list="browsers">
  <datalist id="browsers">
    <option value="Internet Explorer">
    <option value="Firefox">
    <option value="Chrome">
    <option value="Opera">
    <option value="Safari">
  </datalist>
</form>
```

# The `<output>` Element

The `<output>` element represents the result of a calculation (like one performed by a script)

This is code example:

```html
<form action="/action_page.php"
  oninput="x.value=parseInt(a.value)+parseInt(b.value)">
  0
  <input type="range"  id="a" name="a" value="50">
  100 +
  <input type="number" id="b" name="b" value="50">
  =
  <output name="x" for="a b"></output>
  <br><br>
  <input type="submit">
</form>
```

# HTML forms `elements`

![image](https://user-images.githubusercontent.com/119107805/204125397-d7011594-e18e-47b5-b9ab-2e11527a813f.png)

# Input restrictions

![image](https://user-images.githubusercontent.com/119107805/204125455-598efc07-c8a9-410a-aa75-38a690219978.png)

# HTML input types

`<input type="button">`  // defines a button

`<input type="checkbox">` // defines a **checkbox** , checkboxes let a user select ZERO or MORE options of a limited number of choices

`<input type="color">` //is used for **input fields that should contain a color** , is used for input fields that should contain a color

`<input type="date">` // is used for input fields that should contain a date

`<input type="datetime-local">` //specifies a date and time input field, with no time zone

`<input type="email">` // is used for input fields that should contain an e-mail address

`<input type="file">` //defines a file-select field and a "Browse" button for file uploads

`<input type="hidden">` //defines a hidden input field (not visible to a user)

`<input type="image">` //defines an image as a submit button

`<input type="month">` // allows the user to select a month and year

`<input type="number">` //defines a **numeric** input field

`<input type="password">` // defines a **password field**

`<input type="radio">` // defines a **radio button** , radio buttons let a user select ONLY ONE of a limited number of choices

`<input type="range">` //defines a control for entering a number whose exact value is not important (like a slider control). Default range is 0 to 100. However, you can set restrictions on what numbers are accepted with the min, max, and step attributes

`<input type="reset">` //defines a **reset button** that will reset all form values to their default values

`<input type="search">` // is used for search fields (a search field behaves like a regular text field)

`<input type="submit">` // defines a **button for submitting form data to a form-handler**

`<input type="tel">` //  is used for input fields that should contain a telephone number

`<input type="text">` //defines a **single-line text input field**

`<input type="time">` // allows the user to select a time (no time zone)

`<input type="url">` // is used for input fields that should contain a URL address

`<input type="week">` // allows the user to select a week and year

![image](https://user-images.githubusercontent.com/119107805/204125805-a55ca572-e936-4740-8136-c0af0c863d05.png)

# Input Attributes

The input `value` attribute specifies an initial value for an input field

# The readonly Attribute

The input readonly attribute specifies that an input-field is read-only

# The disabled Attribute

The input disabled attribute specifies that an input field should be disabled

# The size Attribute

The input size attribute specifies the visible width, in characters, of an input field

# The maxlength Attribute

The input maxlength attribute specifies the maximum number of characters allowed in an input field

**Note:** When a maxlength is set, the input field will not accept more than the specified number of characters. However, this attribute does not provide any feedback. So, if you want to alert the user, you must write JavaScript code


# The min and max Attributes

The input min and max attributes specify the minimum and maximum values for an input field

# The multiple Attribute

The input multiple attribute specifies that the user is allowed to enter more than one value in an input field

# The pattern Attribute 

The input pattern attribute specifies a regular expression that the input field's value is checked against, when the form is submitted

# The placeholder Attribute
 
 The input placeholder attribute specifies a short hint that describes the expected value of an input field (a sample value or a short description of the expected format)
 
# The required Attribute

The input required attribute specifies that an input field must be filled out before submitting the form

# The step Attribute

The input step attribute specifies the legal number intervals for an input field

# The autofocus Attribute

The input autofocus attribute specifies that an input field should automatically get focus when the page loads

# The height and width Attributes

The input height and width attributes specify the height and width of an <input type="image"> element.

# The list Attribute

The input list attribute refers to a <datalist> element that contains pre-defined options for an <input> element

# The autocomplete Attribute

The input autocomplete attribute specifies whether a form or an input field should have autocomplete on or off.

![image](https://user-images.githubusercontent.com/119107805/204126060-3d6a505e-308f-4b84-b229-8091576ee184.png)



