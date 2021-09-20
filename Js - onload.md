# Onload 

Onload is an Events Part.

the page work in the order in the code .

if you use script in last of the page no error.

but if you want to use in head you should use onload otherwise you have error.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>onload</title>
    <script>
      // Will Wait To Till The Window Is Loaded
      window.onload = function () {
        document.getElementById("test").innerHTML = "Test From Javascript";
      }
    </script>
  </head>
  <body>
    <div id="test"></div>
    <script src="main.js"></script>
  </body>
</html>
```

