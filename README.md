# EUC_Core for EUC_TestBench

Jupyter based EUC data analysis for the community.

## How to add a wheel :
### METADATA
1. Choose a file prefix that will be used to name all files and folders of your wheel. *e.g* : **extreme_C36**
2. create specifications csv file in **build/specs**. Simply copy an existing csv and modify it for the wheel you want to add and save it. *e.g* **build/specs/extreme_C36.csv**

| Field                 | Data                          |
|-----------------------|-------------------------------|
| Brand                 | Begode                        |
| Model                 | Extreme C36                   |
| Year                  | 2025                          |
| Wheel diameter        | 18 inches                     |
| Dimensions            | 460 x 336 x 565 mm (L x W x H) |
| Pedal height          | 120 - 230 mm                  |
| Controller position   | Top                           |
| Tire dimension        | 3.0 R12                       |
| Tubeless              | No                            |
| RGB                   | No                            |
| Water rating          | IP55                          |
| Suspension            | 130 mm, spring-air shock      |
| Max. Load             | 120 kg                        |
| Net weight            | 39 kg                         |
| Trolley               | Included, Central             |
| Range                 | 70-90 km                      |
| Max speed             | 70 km/h                       |
| Motor power           | 3500 W                        |
| Battery               | 2400 Wh                       |
| Tension               | 134.4V                        |
| Battery architecture | 32s4p                         |
| Cells                 | SAMSUNG 50S (21700) li-ion    |
| Smart BMS             | Yes                           |



3. Find an image (jpg, png, webp,...) and put it in **build/imgs/wheels/portrait** *e.g* **imgs/wheels/portrait/extreme_C36.webp**

### TRIPS
1. create a directory tree in the **trips** folder with the following structure : **/BRAND/WHEEL/TRIP_ID** where trip_id is an integer ranging from 0 to 10^31.
For example : **begode/extreme_C36/0**

2. Put your log in the TRIP_ID folder and name it TRIP_ID.csv. *e.g*: **begode/extreme_C36/0/0.csv**

3. Put your trip metadata in a file named **meta.csv** in the TRIP_ID folder. *e.g*: **begode/extreme_C36/0/meta.csv**

4. Make sure your metadata csv file is correct for your current log.

| Wheel        | Brand  | Year | App        | Trip Type | Rider Weight | Tire Pressure | Temperature | Wind | Rain |
|--------------|--------|------|------------|-----------|--------------|---------------|-------------|------|------|
| extreme_C36  | begode | 2024 | euc_world  | 2         | 90           | 2.4           | 10          | mid  | True |


## BUILD

So far this project is based on notebooks, make sure to run the analyze in the following order to get everything correct.

Running scripts in another order will very likely alter the statistics and interpretability.

> A future version should embed everything in a single piece of software.

1. Run **EUC_analysis** to analyze each EUC trip in the **trips** folder.
2. Run **EUC_page** to create each EUC page based on previously analyzed trips.
3. Run **Landing_page** to generate the website landing page based on all data.
4. Everything useful will be available in the **build** folder, that you can subsequently deploy on any Markdown blog :)
