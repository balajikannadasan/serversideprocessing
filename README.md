# Design a Website for Server Side Processing

## AIM:
To design a website to perform mathematical calculations in server side.

## DESIGN STEPS:

### Step 1:
To start the server and open theia IDE.


### Step 2:
Create a folder and Start the django project in that folder.


### Step 3:
Use views.py to execute the coding in serverside.


### Step 4:
Mention the path of the website in urls.py.


### Step 5:
Write a HTML and CSS code for mathematical calculator.


### Step 6:

Publish the website in the given URL.

## PROGRAM :
### main page.html
~~~
<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>
    <meta http-equiv='X-UA-Compatible' content='IE=edge'>
    <title>mathwebsite</title>
    <meta name='viewport' content='width=device-width, initial-scale=1'>
    <script src='main.js'></script>
    <style>
.container {
  width: 1080px;
  margin-left: auto;
  margin-right: auto;
  padding-top: 200px;
  padding-left: 300px;
}
.content {
  display:block;
  width: 500px;
  min-height: 300px;
  font-size: 20px;
  background-color:white;
}
h1{
    color: blue;
    text-align: center;
    padding-top: 25px;
}
.formelement{
    color: blue;
    text-align: center;
    margin-top: 5px;
    margin-bottom: 5px;
}
    </style>
</head>
<body>
    <div class="container">
    <div class="content">
    <h1>VOLUME OF A CYLINDER</h1>
    <form method="POST">
        {% csrf_token %}
        <div class="formelement">
        Length : <input type="text" name="Height" value="{{l}}"></input>Meters<br/>
        </div>
        <div class="formelement">
        Breadth : <input type="text" name="Radius" value="{{b}}"></input>Meters<br/>
        </div>
        <div class="formelement">
        <input type="submit"  value="Calculate Volume"></input><br/>
        </div>
        <div class="formelement">
        Volume : <input type="text" name="volume" value="{{volume}}"></input>Meter<sup>3</sup><br/>
        </div>
    </form>
    </div>
    </div>
</body>
</html>
~~~
### views.py
~~~
from django.shortcuts import render
import numpy as n

def volumecalculation(request):
    context={}
    context['volume'] = "0"
    context['h'] = "0"
    context['r'] = "0"
    if request.method == 'POST':
        l = request.POST.get('Height','0')
        b = request.POST.get('Radius','0')
        volume = n.pi*n.sqrt.int(r)*int(h)
        context['volume'] = volume
        context['h'] = h
        context['r'] = r
    return render(request,'mathapp/volume.html',context)
~~~
### urls.py
~~~
from django.contrib import admin
from django.urls import path
from mathapp import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('volumeofacuboid/',views.volumecalculation,name="volumeofaculinder"),
    path('',views.volumecalculation,name="volumeofacylinderroot")
]
~~~

## OUTPUT:
![output](./1.jpg)


## Result:
Thus a website to perform mathematical calculations in server side is created.
