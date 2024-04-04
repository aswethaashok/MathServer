# Ex.05 Design a Website for Server Side Processing
## Date: 1-4-24

SWETHA A 212223220114
## AIM:
To design a website to find surface area of a Right Cylinder in server side.

## FORMULA:
Surface Area = 2Πrh + 2Πr<sup>2</sup>
<br>r --> Radius of Right Cylinder
<br>h --> Height of Right Cylinder

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
'''
math.html

<html>
    
<head>
    
<meta charset='utf-8'>

<meta http-equiv='X-UA-Compatible' content='IE=edge'>

<title>Area of a Square prism</title>

<meta name='viewport' content='width=device-width, initial-scale=1'>

<style type="text/css">
    
body 
    
{
    
background-color:rgb(14, 192, 227);
    
}
    
.edge {
    
width: 1440px;
    
margin-left: auto;
    
margin-right: auto;
    
padding-top: 300px;
    
padding-left: 300px;
    
}
    
.box {
    
display:inline-block;
    
border: Thick lightgoldenrodyellow(100, 100, 156);
    
width: 500px;
    
min-height: 300px;
    
font-size: 20px;
    
background-color:rgb(121, 205, 11);
    
}
    
.formelt{
    
color:rgb(25, 31, 30);
    
text-align: center;
    
margin-top: 7px;
    
margin-bottom: 6px;
    
}
    
h1
    
{
    
color:rgb(25, 58, 123);
    
text-align: center;
    
padding-top: 20px;
    
}
    
</style>

</head>

<body>
    
<div class="edge">
    
<div class="box">
    
SWETHA A (212223220114) 

<h1>Surface Area </h1>

<form method="POST">
    
{% csrf_token %}

<div class="formelt">
    
Radius : <input type="text" name="radius" value="{{r}}"></input>(in m)<br/>

</div>

<div class="formelt">
    
Height : <input type="text" name="height" value="{{h}}"></input>(in m)<br/>

</div>

<div class="formelt">
    
<input type="submit" value="2Πrh + 2Πr2"></input><br/>

</div>

<div class="formelt">
    
Area : <input type="text" name="area" value="{{area}}"></input>m<sup>2</sup><br/>

</div>

</form>

</div>

</div>

</body>

</html>

'''

views.py

'''

from django.shortcuts import render

def surfacearea(request):

    context={}
    
    context['area'] = "0"
    
    context['r'] = "0"
    
    context['h'] = "0"
    
    if request.method == 'POST':
    
        print("POST method is used")
        
        r = request.POST.get('radius','0')
        
        h = request.POST.get('height','0')
        
        print('request=',request)
        
        print('radius=',r)
        
        print('height=',h)
        
        area = 2 * 3.14 * int(r) * int(h) + 2 * 3.14 * int(r) * int(r)
        
        context['area'] = area
        
        context['r'] = r
        
        context['h'] = h
        
        print('Area=',area)
        
    return render(request,'mathapp/math.html',context)
    
'''

urls.py

'''

from django.contrib import admin

from django.urls import path

from mathapp import views

urlpatterns = [

    path('admin/', admin.site.urls),
    
    path('surfaceareaofcylinder/',views.surfacearea,name="surfaceareaofcylinder"),
    
    path('',views.surfacearea,name="surfaceareaofcylinderroot")
    
]

'''

## SERVER SIDE PROCESSING:

![Screenshot 2024-04-03 210447](https://github.com/aswethaashok/MathServer/assets/149987410/2df2725b-b923-491a-941f-0b1dc8c5f9fb)


## HOMEPAGE:

![Screenshot 2024-04-04 111846](https://github.com/aswethaashok/MathServer/assets/149987410/af19eee2-baee-4dad-b962-6ed7ffaae081)




## RESULT:
The program for performing server side processing is completed successfully.
