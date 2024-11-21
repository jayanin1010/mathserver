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
    
    class PowerCalculation(models.Model):
        intensity = models.IntegerField()
        resistance = models.IntegerField()
        power = models.FloatField()


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

HOMEPAGE:

RESULT:
The program for performing server side processing is completed successfully.
