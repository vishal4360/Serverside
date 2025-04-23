# Ex.05 Design a Website for Server Side Processing
## Date:23/04/2025

## AIM:
 To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side. 


## FORMULA:
P = I<sup>2</sup>R
<br> P --> Power (in watts)
<br> I --> Intensity
<br> R --> Resistance

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
front.html
```
<html>
<head>
<meta charset='utf-8'>
<meta http-equiv='X-UA-Compatible' content='IE=edge'>
<title>SURFACE AREA OF RIGHT CYLINDER</title>
<h2 align="center">VISHAL C</h2>
<h3 align="center">212224100062</h3>
<meta name='viewport' content='width=device-width, initial-scale=1'>
<style type="text/css">
body {
    background-color: rgb(207, 155, 59);
}
.edge {
    width: 100%; /* Set width to 100% */
    display: flex;
    justify-content: center; /* Center the content horizontally */
    align-items: center; /* Center the content vertically */
    height: 100vh; /* Set height to 100% of the viewport height */
}
.box {
    border: Thick dashed rgb(193, 117, 18);
    width: 500px;
    min-height: 300px;
    font-size: 20px;
    background-color: pink;
    padding: 20px; /* Add padding for better appearance */
}
.formelt {
    color: black;
    text-align: center;
    margin-top: 7px;
    margin-bottom: 6px;
}
h1 {
    color: black;
    text-align: center;
    padding-top: 20px;
}
</style>
</head>
<body>
<div class="edge">
    <div class="box">
        <h1>SURFACE AREA OF RIGHT CYLINDER </h1>
        <form method="POST">
            {% csrf_token %}
            <div class="formelt">
                Radius : <input type="text" name="Radius" value="{{ r }}"></input>(in m)<br/>
            </div>
            <div class="formelt">
                Height : <input type="text" name="height" value="{{ h }}"></input>(in m)<br/>
            </div>
            <div class="formelt">
                <input type="submit" value="Calculate"></input><br/>
            </div>
            <div class="formelt">
                Area : <input type="text" name="area" value="{{ area }}"></input>m<sup>2</sup><br/>
            </div>
        </form>
    </div>
</div>
</body>
</html>
```
urls.py
```
from django.contrib import admin
from django.urls import path
from ssapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('areaofrightcylinder/',views.rightcylinder,name="areaofrightcylinder"),
    path('',views.rightcylinder,name="areaofrightcylinderroot")
]
```
views.py
```
from django.shortcuts import render
def rightcylinder(request):
    context = {}
    context['area'] = "0"
    context['r'] = "0"
    context['h'] = "0"
    
    if request.method == 'POST':
        print("POST method is used")
        
        # Print the entire request.POST object
        print('request.POST:', request.POST)
        
        r = request.POST.get('Radius', '0')  # Corrected key to retrieve radius
        h = request.POST.get('height', '0')  # Corrected key to retrieve height
        print('radius =', r)
        print('height =', h)
        
        area = (2 * 3.14 * int(r) * int(h)) + (2 * 3.14 * int(r) * int(r))
        context['area'] = area
        context['r'] = r
        context['h'] = h
        print('Area =', area)
    
    return render(request, 'ssapp/front.html', context)

```

## SERVER SIDE PROCESSING:


## HOMEPAGE:


## RESULT:
The program for performing server side processing is completed successfully.
