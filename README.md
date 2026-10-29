JWP Practical Experiment: Online Book Store

AIM

To design static web pages required for an online book store using HTML frames, hyperlinks, tables, and forms.

ALGORITHM

1. Create the home page using HTML frames.
2. Create the top frame containing the college name and navigation links.
3. Create the left frame containing department links.
4. Create the right frame to display the home page and other contents.
5. Create Login, Registration, Catalogue, and Order Confirmation pages.
6. Link all pages using hyperlinks and frame targets.
7. Execute "home.html" in a web browser.

PROGRAM

1. home.html

<html>
<head>
    <title>Online Book Store</title>
</head>

<frameset rows="40%,60%">
    <frame src="top.html" name="topframe"
           scrolling="NO" noresize>

    <frameset cols="15%,85%">
        <frame src="left.html" name="leftframe"
               scrolling="NO" noresize>

        <frame src="right.html" name="rightframe">
    </frameset>
</frameset>

</html>

2. top.html

<html>
<head>
    <title>Top Frame</title>
</head>

<body bgcolor="YellowGreen">

<center>
    <h1>Online Book Store</h1>
    <h3>Created & Maintained By MRCET</h3>

    <table width="100%" height="50%">
        <tr align="center">
            <td>
                <a href="right.html" target="rightframe">
                    HOME
                </a>
            </td>

            <td>
                <a href="login.html" target="rightframe">
                    LOGIN
                </a>
            </td>

            <td>
                <a href="registration.html" target="rightframe">
                    REGISTER
                </a>
            </td>

            <td>
                <a href="catalogue.html" target="rightframe">
                    CATALOGUE
                </a>
            </td>
        </tr>
    </table>
</center>

</body>
</html>

3. left.html

<html>
<body bgcolor="bisque">

<center>
    <h3>
        <a href="cse.html" target="rightframe">CSE</a>
        <br><br>

        <a href="ece.html" target="rightframe">ECE</a>
        <br><br>

        <a href="eee.html" target="rightframe">EEE</a>
        <br><br>

        <a href="mech.html" target="rightframe">MECH</a>
    </h3>
</center>

</body>
</html>

4. right.html

<html>
<body bgcolor="orange">

<center>
    <h2>Welcome to the Online Book Store</h2>

    <h3>
        A Huge Collection of Engineering E-Books
    </h3>
</center>

</body>
</html>

5. cse.html

<html>
<head>
    <title>CSE</title>
</head>

<body bgcolor="cyan">

<center>
    <h1>Computer Science and Engineering</h1>

    <table align="center" border="1">
        <tr>
            <th>Text Books</th>
        </tr>
        <tr>
            <td>Web Technologies</td>
        </tr>
        <tr>
            <td>Java Programming</td>
        </tr>
        <tr>
            <td>Computer Networks</td>
        </tr>
    </table>
</center>

</body>
</html>

6. ece.html

<html>
<head>
    <title>ECE</title>
</head>

<body bgcolor="Plum">

<center>
    <h1>Electronics and Communication Engineering</h1>

    <h3>
        <ul>
            <li>Digital Circuits</li>
            <li>Signals and Systems</li>
            <li>Digital Communication</li>
        </ul>
    </h3>
</center>

</body>
</html>

7. eee.html

<html>
<head>
    <title>EEE</title>
</head>

<body bgcolor="Plum">

<center>
    <h1>Electrical and Electronics Engineering</h1>

    <h3>
        <ul type="square">
            <li>Concepts in Electric Circuits</li>
            <li>Introduction to Electronic Engineering</li>
            <li>Electrical Power</li>
        </ul>
    </h3>
</center>

</body>
</html>

8. mech.html

<html>
<head>
    <title>MECH</title>
</head>

<body bgcolor="Plum">

<center>
    <h1>Mechanical Engineering</h1>

    <h3>
        <ol type="I">
            <li>Theory of Machines</li>
            <li>Automation and Robotics</li>
            <li>Engineering Fluid Mechanics</li>
        </ol>
    </h3>
</center>

</body>
</html>

9. catalogue.html

<html>
<head>
    <title>Catalogue</title>
</head>

<body bgcolor="pink">

<center>
    <h2>Book Catalogue</h2>

    <table border="1" width="100%">
        <tr>
            <th>Book Name</th>
            <th>Author</th>
            <th>Publisher</th>
            <th>Price</th>
            <th>Action</th>
        </tr>

        <tr>
            <td>Web Technologies</td>
            <td>Uttam K. Roy</td>
            <td>Oxford University Press</td>
            <td>531</td>
            <td>
                <form action="order.html">
                    <input type="submit" value="Add to Cart">
                </form>
            </td>
        </tr>

        <tr>
            <td>PHP & MySQL Web Development</td>
            <td>Luke Welling & Laura Thomson</td>
            <td>Pearson</td>
            <td>898</td>
            <td>
                <form action="order.html">
                    <input type="submit" value="Add to Cart">
                </form>
            </td>
        </tr>
    </table>

    <p>Cost of one book = Book price + Shipping charges</p>
</center>

</body>
</html>

10. login.html

<html>
<head>
    <title>Login</title>
</head>

<body bgcolor="pink">

<center>
    <h2>Enter Login Details</h2>

    <form action="right.html" method="post">
        <table>
            <tr>
                <td>Login ID:</td>
                <td>
                    <input type="text" name="userid">
                </td>
            </tr>

            <tr>
                <td>Password:</td>
                <td>
                    <input type="password" name="password">
                </td>
            </tr>

            <tr>
                <td>
                    <input type="submit" value="Submit">
                </td>
                <td>
                    <input type="reset" value="Reset">
                </td>
            </tr>
        </table>
    </form>
</center>

</body>
</html>

11. registration.html

<html>
<head>
    <title>Registration Form</title>
</head>

<body bgcolor="#E4F0F8">

<center>
    <h2>Registration Form</h2>

    <form action="right.html">
        First Name:
        <input type="text" name="firstname"
               minlength="6" required>
        <br><br>

        Last Name:
        <input type="text" name="lastname">
        <br><br>

        Email Address:
        <input type="email" name="email" required>
        <br><br>

        Password:
        <input type="password" name="pass"
               minlength="6" required>
        <br><br>

        Address:
        <textarea rows="2" cols="20" name="address"></textarea>
        <br><br>

        Mobile No:
        <input type="tel" name="mobile">
        <br><br>

        Gender:
        <input type="radio" name="gender" value="male">
        Male

        <input type="radio" name="gender" value="female">
        Female
        <br><br>

        <input type="submit" value="Submit">
        <input type="reset" value="Reset">
    </form>
</center>

</body>
</html>

12. order.html

<html>
<head>
    <title>Order Confirmation</title>
</head>

<body bgcolor="cyan">

<center>
    <h2>Your Order Is Confirmed</h2>

    <h2>THANK YOU... Visit Again</h2>
</center>

</body>
</html>

PROCEDURE

1. Open Visual Studio Code.
2. Create a folder named "OnlineBookStore".
3. Create all twelve HTML files given above.
4. Copy the respective programs into each file and save them.
5. Keep all files in the same folder.
6. Open "home.html" in a web browser.
7. Test the navigation links and forms.

RESULT

Thus, the static web pages for an Online Book Store were designed and executed successfully using HTML.

NOTE

This is a static HTML project. Login, registration, and order confirmation pages demonstrate form navigation only; they do not store user details, authenticate users, or process actual purchases.

# Online Book Store – JWP Practical

## home.html
```html
<html>
<head>
<title>Online Book Store</title>
</head>
<frameset rows="40%,60%">
<frame src="top.html" name="topframe" scrolling="NO" noresize>
<frameset cols="15%,85%">
<frame src="left.html" name="leftframe" scrolling="NO" noresize>
<frame src="right.html" name="rightframe">
</frameset>
</frameset>
</html>
```

## top.html
```html
<html>
<head>
<title>Top Frame</title>
</head>
<body bgcolor="YellowGreen">
<center>
<h1>Online Book Store</h1>
<h3>Created & Maintained By MRCET</h3>
<table width="100%" height="50%">
<tr align="center">
<td><a href="right.html" target="rightframe">HOME</a></td>
<td><a href="login.html" target="rightframe">LOGIN</a></td>
<td><a href="registration.html" target="rightframe">REGISTER</a></td>
<td><a href="catalogue.html" target="rightframe">CATALOGUE</a></td>
</tr>
</table>
</center>
</body>
</html>
```

## left.html
```html
<html>
<body bgcolor="bisque">
<center>
<h3>
<a href="cse.html" target="rightframe">CSE</a><br><br>
<a href="ece.html" target="rightframe">ECE</a><br><br>
<a href="eee.html" target="rightframe">EEE</a><br><br>
<a href="mech.html" target="rightframe">MECH</a>
</h3>
</center>
</body>
</html>
```

## right.html
```html
<html>
<body bgcolor="orange">
<center>
<img src="images/Books.jpg" height="170"><br>
<h2>Welcome to the Online Book Store</h2>
<h3>A Huge Collection of Engineering E-Books</h3>
</center>
</body>
</html>
```

## cse.html
```html
<html>
<head>
<title>CSE</title>
</head>
<body bgcolor="cyan">
<center>
<h1>Computer Science and Engineering</h1>
<table align="center" border="1">
<tr><th>Text Books</th></tr>
<tr><td>Web Technologies</td></tr>
<tr><td>Java Programming</td></tr>
<tr><td>Computer Networks</td></tr>
</table>
</center>
</body>
</html>
```

## ece.html
```html
<html>
<head>
<title>ECE</title>
</head>
<body bgcolor="Plum">
<center>
<h1>Electronics and Communication Engineering</h1>
<h2>
<ul>
<li>Digital Circuits</li>
<li>Signals and Systems</li>
<li>Digital Communication</li>
</ul>
</h2>
</center>
</body>
</html>
```

## eee.html
```html
<html>
<head>
<title>EEE</title>
</head>
<body bgcolor="Plum">
<center>
<h1>Electrical and Electronics Engineering</h1>
<h2>
<ul type="square">
<li>Concepts in Electric Circuits</li>
<li>Introduction to Electronic Engineering</li>
<li>Electrical Power</li>
</ul>
</h2>
</center>
</body>
</html>
```

## mech.html
```html
<html>
<head>
<title>MECH</title>
</head>
<body bgcolor="Plum">
<center>
<h1>Mechanical Engineering</h1>
<h2>
<ol type="I">
<li>Theory of Machines</li>
<li>Automation and Robotics</li>
<li>Engineering Fluid Mechanics</li>
</ol>
</h2>
</center>
</body>
</html>
```

## catalogue.html
```html
<html>
<head>
<title>Catalogue</title>
</head>
<body bgcolor="pink">
<center>
<h2>Book Catalogue</h2>
<table border="1" width="100%">
<tr>
<th>Book Name</th>
<th>Author</th>
<th>Publisher</th>
<th>Price</th>
<th>Action</th>
</tr>
<tr>
<td>Web Technologies</td>
<td>Uttam K. Roy</td>
<td>Oxford University Press</td>
<td>531</td>
<td>
<form action="order.html">
<input type="submit" value="Add to Cart">
</form>
</td>
</tr>
<tr>
<td>PHP & MySQL Web Development</td>
<td>Luke Welling & Laura Thomson</td>
<td>Pearson</td>
<td>898</td>
<td>
<form action="order.html">
<input type="submit" value="Add to Cart">
</form>
</td>
</tr>
</table>
<p>Cost of one book = Book price + Shipping charges</p>
</center>
</body>
</html>
```

## login.html
```html
<html>
<head>
<title>Login</title>
</head>
<body bgcolor="pink">
<center>
<h2>Enter Login Details</h2>
<form action="right.html" method="post">
<table>
<tr>
<td>Login ID:</td>
<td><input type="text" name="userid"></td>
</tr>
<tr>
<td>Password:</td>
<td><input type="password" name="password"></td>
</tr>
<tr>
<td><input type="submit" value="Submit"></td>
<td><input type="reset" value="Reset"></td>
</tr>
</table>
</form>
</center>
</body>
</html>
```

## registration.html
```html
<html>
<head>
<title>Registration Form</title>
</head>
<body bgcolor="#E4F0F8">
<center>
<h2>Registration Form</h2>
<form action="right.html">
First Name:
<input type="text" name="firstname" minlength="6" required><br><br>

Last Name:
<input type="text" name="lastname"><br><br>

Email Address:
<input type="email" name="email" required><br><br>

Password:
<input type="password" name="pass" minlength="6" required><br><br>

Address:
<textarea rows="2" cols="20" name="address"></textarea><br><br>

Mobile No:
<input type="tel" name="mobile"><br><br>

Gender:
<input type="radio" name="gender" value="male">Male
<input type="radio" name="gender" value="female">Female
<br><br>

<input type="submit" value="Submit">
<input type="reset" value="Reset">
</form>
</center>
</body>
</html>
```

## order.html
```html
<html>
<head>
<title>Order Confirmation</title>
</head>
<body bgcolor="cyan">
<center>
<h2>Your Order Is Confirmed</h2>
<h2>THANK YOU... Visit Again</h2>
</center>
</body>
</html>
```
