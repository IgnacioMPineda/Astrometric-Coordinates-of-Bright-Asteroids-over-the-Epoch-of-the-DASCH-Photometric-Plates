# Astrometric-Coordinates-of-Bright-Asteroids-over-the-Epoch-of-the-DASCH-Photometric-Plates
Computing the Astrometric Coordinates of Bright Asteroids over the Epoch of the DASCH Photometric Plates. Work to be presented in King's College London the 31st of january, 2026. Will conclude in an academic paper.

The Harvard College Observatory's Astronomical Photographic Glass Plate Collection (Plate Stacks) is the largest collection of its kind in the world, with over 550.000 plates that cover both hemispheres.

It nearly covers a hundred years of work and is the first full image of the observable universe. Hundreds of women worked on the plates but the circumstances of their time made it so that they didn’t receive the merit they'd reserved.
The Dasch project aimed to digitalize and immortalize this information whilst bringing awareness to the work done by these women, whilst also allowing for further use in research projects. My individual project was to use these plates and computationally plot the astrometric coordinates of certain asteroids, allowing for further investigation.

The asteroids chosen have an apparent magnitude under 17 and are considered “bright”. These have a semimajor axis around 1.5 AU.



Datafile larger than 10 MB are saved to google drive here

https://drive.google.com/drive/folders/1s8QCIX3pKO5bhGDZRLQEm9xMqVIvIvRI?usp=drive_link

The file "Observability.json" is required for plotting the statistics of the asteroids.

The file 

## Project Flowchart
```text
initial_conditions.*
        |
        v
+--------------------+
| integrator.*       |
| integrates ALL     |
| asteroids          |
| light-time corr.   |
+--------------------+
        |
        v
integrated_asteroids.*
        |
        v
+--------------------+
| filtering.*        |
| keeps asteroids    |
| observed in plates |
+--------------------+
        |
        v
observability.json
coords + obs time + plate
        |
        v
+--------------------+
| astroquery_*.py    |
| plate + coords     |
| -> cutout image    |
+--------------------+
        |
        v
cutout_image.*
        |
        v
+--------------------+
| fitting_script.*   |
| image -> position  |
| brightness + error |
+--------------------+
        |
        v
fit_results.*
```
