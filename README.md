# Flask Templates

### App structure

This project builds on the [hello-flask repo](https://github.com/ChristinaVoss/hello_flask) but adds some super simple templates. We will just demonstrate the intruduction of them here, but will add more complex examples in other demonstrations. 

<img width="618" alt="Screenshot 2022-05-12 at 09 37 39" src="https://user-images.githubusercontent.com/20923607/168029003-767cba25-2f86-41e1-a0d9-7d840137655c.png">

**Key parts**

The templates directory - Flask will look for a templates directory, so the easiest way to add them is to include this directory.

In app.py:

Import render_template from flask

`from flask import Flask, render_template`

Then you can use render_template in your controller and pass it variables:

```
@app.route("/")
def index():
    user = "Christina"
    return render_template('index.html', user=user)
```

In index.html, write normal html, and where you need dynamic features use Jinja2 (in later demos we add inheritance and more). `{{ ... }}` will output experssions to the browser. Use {% ... %} for Python statements:

```
<h1>Hello {{ user }}</h1>
{% if user == "Christina" %}
  <p>You like cats!</p>
{% else %}
  <p>You like dogs?</p>
{% endif %}
```

### Setup

First create and activate some form of environment to store your dependencies. I like Anaconda:

```
$ conda create -n myenv python=3.7

$ conda activate myenv
```

Then install Flask

`$ pip install Flask`

### Run the app

`$ flask run`

You should now be able to see the output in your browser window (at http://127.0.0.1:5000) 

### Screenshot of browser with app running


<img width="517" alt="Screenshot 2022-05-12 at 17 59 56" src="https://user-images.githubusercontent.com/20923607/168129511-ac65c1c3-cfc8-466b-ae2d-4ba4c466809f.png">
