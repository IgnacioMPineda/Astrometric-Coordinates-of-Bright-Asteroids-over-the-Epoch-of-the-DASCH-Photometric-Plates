# Astrometric-Coordinates-of-Bright-Asteroids-over-the-Epoch-of-the-DASCH-Photometric-Plates
Computing the Astrometric Coordinates of Bright Asteroids over the Epoch of the DASCH Photometric Plates. Work to be presented in King's College London the 31st of january, 2026. Will conclude in an academic paper.

The Harvard College Observatory's Astronomical Photographic Glass Plate Collection (Plate Stacks) is the largest collection of its kind in the world, with over 550.000 plates that cover both hemispheres.

It nearly covers a hundred years of work and is the first full image of the observable universe. Hundreds of women worked on the plates but the circumstances of their time made it so that they didn’t receive the merit they'd reserved.
The Dasch project aimed to digitalize and immortalize this information whilst bringing awareness to the work done by these women, whilst also allowing for further use in research projects. My individual project was to use these plates and computationally plot the astrometric coordinates of certain asteroids, allowing for further investigation.

The asteroids chosen have an apparent magnitude under 17 and are considered “bright”. These have a semimajor axis around 1.5 AU.

Datafile larger than 10 MB are saved to google drive here

https://drive.google.com/drive/folders/1s8QCIX3pKO5bhGDZRLQEm9xMqVIvIvRI?usp=drive_link

## Project Flowchart

+--------------------------------------------------------------+
| [FILENAME: initial_conditions.*]                             |
| Initial conditions for ALL asteroids                         |
+-----------------------------+--------------------------------+
                              |
                              |
                              v
        +---------------------------------------------+
        | [SCRIPT: integrator.*]                      |
        | - Integrates asteroids to target times      |
        | - Applies light-time correction             |
        | - Processes ALL asteroids                   |
        +---------------------+-----------------------+
                              |
                              |
                              v
+--------------------------------------------------------------+
| [FILENAME: integrated_asteroids.*]                           |
| Integrated asteroid positions / ephemerides                  |
+-----------------------------+--------------------------------+
                              |
                              |
                              v
        +---------------------------------------------+
        | [SCRIPT: filtering.*]                       |
        | - Takes initial/integrated asteroid data    |
        | - Keeps only asteroids observed in plates   |
        | - Builds observability table                |
        +---------------------+-----------------------+
                              |
                              |
                              v
+--------------------------------------------------------------+
| [FILENAME: observability.json]                               |
| For each observed asteroid:                                  |
| - coordinates                                                |
| - time of observation                                        |
| - plate where it was observed                                |
+-----------------------------+--------------------------------+
                              |
                              |
                              v
        +---------------------------------------------+
        | [SCRIPT: astroquery_cutouts.*]              |
        | Input: plate + coordinates                  |
        | Output: image cutout                        |
        +---------------------+-----------------------+
                              |
                              |
                              v
+--------------------------------------------------------------+
| [FILENAME: cutout_image.*]                                   |
| Plate image cutout around asteroid coordinates               |
+-----------------------------+--------------------------------+
                              |
                              |
                              v
        +---------------------------------------------+
        | [SCRIPT: fitting_script.*]                  |
        | Input: image cutout                         |
        | Output: fit result                          |
        | - position                                  |
        | - brightness                                |
        | - error bar                                 |
        +---------------------+-----------------------+
                              |
                              |
                              v
+--------------------------------------------------------------+
| [FILENAME: fit_results.*]                                    |
| Asteroid fitted position, brightness, and uncertainties       |
+--------------------------------------------------------------+
