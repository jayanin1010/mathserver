# Ex.05 Design a Website for Server Side Processing
# Date:19-10-2024
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
P = I2R
P --> Power (in watts)
 I --> Intensity
 R --> Resistance

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :

# views.py

    from django.shortcuts import render

    def calculate_power(request):
        if request.method == 'POST':
            intensity = int(request.POST.get('intensity'))
            resistance = int(request.POST.get('resistance'))
            power = ((intensity)*(intensity))*resistance
            return render(request, 'result.html', {'power': power})
        return render(request, 'index.html')


# urls.py 

    from django.urls import path
    from . import views

    urlpatterns = [
        path('', views.calculate_power, name='calculate_power'),
    ]



# index.html

     <body style="background-color: bisque;">
     <center>
     <h1>Lamp Filament Power Calculator</h1>
 
     <form method="post">
     {% csrf_token %}
     <label for="intensity">Intensity (in lumens):</label>
     <input type="number" id="intensity" name="intensity" required><br><br>
 
     <label for="resistance">Resistance (in ohms):</label>
     <input type="number" id="resistance" name="resistance" required><br><br>
 
     <button type="submit">Calculate Power</button>
     </form>
     </center>
     </body>




# result.html

     <body style="background-color: aquamarine;">
 
     </body><center>
 
     <h1>Result</h1>
     <p>The power of the lamp filament is {{ power }} watts.</p>
     </center>
     </body>


# SERVER SIDE PROCESSING:



![image](https://github.com/user-attachments/assets/6ae130bd-6c12-4db9-b734-c83079a72a45)

# Homepage 

![alt text](image-1.png)

![image](https://github.com/user-attachments/assets/2b127eb1-f0a9-4d2c-9c77-3453d94020bf)

![alt text](image.png)






# RESULT:
The program for performing server side processing is completed successfully.
