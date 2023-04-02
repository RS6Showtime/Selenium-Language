# Selenium Language

[Powered by Mix-Panel.Ro](https://mix-panel.ro/) 

# Info

We currently support only Windows and xpath as primary method and to acces html elements.

# How to use

<pre>
Usage: mix-panel --script-name <script name>
</pre>

should end in ".mxp" and have some valid instructions.

# Documentation

Start Browser:

```javascript
# Start Browser
start(111)
```

start() means the start of chrome webdriver

<pre>
1. Chrome version
</pre>

Inserting options:

```javascript
# Start Options
start_options()

# Add Option
option("--disable-popup-blocking")
option("--disable-notifications")
```

start_options() will means we will use chrome options, and option() where we add our chrome options.

<pre>
1. Chrome option
</pre>

Navigate:

```javascript
# Navigate
navigate("https://mix-panel.ro/selenium/example/index.html")
```

navigate() is used going to a specific website where it can be reached in current tab.

<pre>
1. URL
</pre>

Select Options:

```javascript
# Select From Html Options portocala
select_option("xpath", "/html/body/div[1]/select", "Mar", "portocala")
```

select_option() is used to select an option from a html code.

Example:

```html
<select name="fructe">
  <option value="mar">Mar</option>
  <option value="para">Para</option>
  <option value="portocala">Portocala</option>
  <option value="kiwi">Kiwi</option>
</select>
```

<pre>
1. "xpath" as default
2. xpath element
3. Visible(First) text
4. Value to select
</pre>

Save Element Value:

```javascript
# Save First H1 Value
save_element("xpath", "/html/body/h1[1]")
```

save_element() is used to save an element value to an array that can be used later.

<pre>
1. "xpath" as default
2. xpath element
</pre>

Save Attribute value:

```javascript
# Save Second H1 Value, but via it's attribute
save_attribute("xpath", "/html/body/h1[2]", "value")
```

save_attribute() is used to save an element attribute value to an array that can be used later.

<pre>
1. "xpath" as default
2. xpath element
3. attribute name
</pre>

Print Saved Elements:

```javascript
# Print Saved Element And Attribute Value
print_element(0)
print_element(1)
```

print_element() is used to print in console the value of a html element and his xpath.

<pre>
1. Number
</pre>

Get Element Value:

```javascript
get_value(1)
```

get_value() will return the value of the html element. (Same as print_element, but will return only his value). You can also store into a variable and use it later. REMEMBER: you should not call this if you won't store it into any kind of variable.

```javascript
secret_value = get_value(1)
```

Click Element and Insert Data:

```javascript
# Click Input And Insert secret_value Into Input Text
click_element("xpath", '//input')
send_value(secret_value)
```

click_element() is used to click an clickable element.

<pre>
1. "xpath" as default
2. xpath element
</pre>

send_value() is used to insert value into clicked element. (If an element wasn't clicked it won't work).

<pre>
1. Data(Value)
</pre>

Executing Java:

```javascript
# Execute Java Script
execute_java('''window.open("http://mix-panel.ro");''', "_blank")
```

execute_java() is used to execute any kind of java in the browser.

<pre>
1. Javascript Code
2. Args
</pre>

Sleeping Program:

```javascript
# Sleep Time
sleep_time(1)
```

sleep_time() is used to wait for a specific time before doing another operation.

<pre>
1. Sleep Time (Number)
</pre>

Switch Tab:

```javascript
switch_tab(0)
```
switch_tab() is used to switch the tab and the environment where webdriver will execute the operations.

<pre>
1. Tab to Switch (Number)
</pre>

Generate Text:

```javascript
# Generated Text | Length
password = generate(20)
```

generate() is used to generate random text with characters.

<pre>
1. Text Lenght (Number)
</pre>

Repeat Stuff:

```javascript
repeat(3, 0.5)
```

repeat() is used to execute saved repeated functions for a specific time and making the program to wait before executing. REMEMBER that the sleep is firstly executed and the the operation.

<pre>
1. Execute Time (Number)
2. Sleep Time (Number)
</pre>

Save Functions for Repeat:

```javascript
save_repeat('select_option("xpath", "/html/body/div[1]/select", "Mar", "portocala")')
save_repeat('select_option("xpath", "/html/body/div[1]/select", "Portocala", "mar")')
```

save_repeat() is used to save the function to an array and use it later using repeat();

<pre>
1. Function
</pre>


Exit Program:

```javascript
exit_program()
```

exit_program() is used to close the chrome webdriver and terminate immediately the program.

# Support this project

<a href="https://www.paypal.com/donate/?business=WPGWD3YJ7GZ9W&no_recurring=0&item_name=Support+me+for+more+github+projects.&currency_code=EUR">
  <img src="https://raw.githubusercontent.com/stefan-niedermann/paypal-donate-button/master/paypal-donate-button.png" alt="Donate with PayPal" />
</a>

