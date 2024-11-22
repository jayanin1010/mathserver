Ex.05 Design a Website for Server Side Processing
Date:
AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

FORMULA:
P = I2R P --> Power (in watts) I --> Intensity R --> Resistance

DESIGN STEPS:
Step 1:
Clone the repository from GitHub.

Step 2:
Create Django Admin project.

Step 3:
Create a New App under the Django Admin project.

Step 4:
Create python programs for views and urls to perform server side processing.

Step 5:
Create a HTML file to implement form based input and output.

Step 6:
Publish the website in the given URL.

PROGRAM :

# lamp_power_app/models.py
    from django.db import models
    from django.contrib import admin
    
    class PowerCalculation(models.Model):
        intensity = models.IntegerField()
        resistance = models.IntegerField()
        power = models.FloatField()

    class PowerAdmin(admin.ModelAdmin):
    list_display=('intensity','resistance','power')


# lamp_power_app/admin.py

        from django.contrib import admin
        
        from .models import PowerCalculation,PowerAdmin
        
        admin.site.register(PowerCalculation,PowerAdmin)
    


# lamp_power_app/views.py
    from django.shortcuts import render
    
    def calculate_power(request):
        if request.method == 'POST':
            intensity = int(request.POST.get('intensity'))
            resistance = int(request.POST.get('resistance'))
            power = intensity / resistance
            return render(request, 'result.html', {'power': power})
        return render(request, 'index.html')


# lamp_power_app/templates/index.html
    <h1>Lamp Filament Power Calculator</h1>
    
    <form method="post">
        {% csrf_token %}
        <label for="intensity">Intensity (in lumens):</label>
        <input type="number" id="intensity" name="intensity" required><br><br>
    
        <label for="resistance">Resistance (in ohms):</label>
        <input type="number" id="resistance" name="resistance" required><br><br>
    
        <button type="submit">Calculate Power</button>
</form>

# lamp_power_app/templates/result.html
    <h1>Result</h1>
    <p>The power of the lamp filament is {{ power }} watts.</p>


SERVER SIDE PROCESSING: 

![image](https://github.com/user-attachments/assets/abbc4a73-baf8-47f7-975a-a46d5db2bc55)


HOMEPAGE:

![image](https://github.com/user-attachments/assets/7ff0f376-aeca-41d0-9365-61ca142da1e8)


RESULT:
The program for performing server side processing is completed successfully.
