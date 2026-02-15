# Habit and Weight Tracking
A collection of R scripts to help visualize various progress in weight change or other habits.

## Original Intent
This project was started as just a weight tracker for my wife and me. And then I realized I wanted other habits tracked as well. The code is similar enough that it felt odd to recreate it completely, and their related areas in my life so I want to keep them bundled together.

# Habit-Tracker
This is the R script dedicated to visualizing progress on keeping a daily habit. Rather than simply counting streaks that get reset if you miss a day, it plots a line showing the percentage of completion for a given period. If you keep a habit daily from start to end, the line will be linear from zero to one hundred percent. Miss a few days, and the final percentage at the end of the chosen period will be less than 100%. The hope is that an upward increasing line will encourage progress more than a hard reset on a streak or a gradually decreasing score from perfect to reality. 

## How to Use
1. Put a csv file in the data folder with a column for the date and for whatever habit you want to track. Have as many columns as you like, but know that all habits will be put on the same plot. Too many, and the figure will get crowded.
  - the csv file name should have the format: "{name}_habit.csv"
  - the date should be formatted "yyyy-mm-dd"
2. Adjust the start date and number of weeks to plot in the script itself. It's at the top.
3. Run the script by opening an R console and using the command "Rscript habit-tracker.R"
4. Check the output folder for the resultant plot.

## Features
- Tracks all your habits on a single plot. Any one habit lagging behind will stick out from the others.
- Automatically assigns colors and legend to whatever habits your put in your csv file.

# Weight-Tracker

## How to Use
1. Put a csv file with dates and weight in the data folder.
  - The file name should follow the form "{name}_{height in inches}_{weekly weight change}_weight.csv".
  - {name} is a string.
  - {height} is an integer.
  - {weekly weight change} is a double. Negative for weight loss, positive for weight gain. Leave out to not plot a goal line.
  - The first column 'date' has format "yyyy-mm-dd".
  - The second column ' weight' is a dbl value representing weight in pounds.
2. Adjust the start date and number of weeks to plot by setting those values in the script. They're at the top.
3. Run the script in an R console, using the command "Rscript weight-tracker.R"
3. Check the output folder. The resultant plots end up there.

## Features
- Iterates through every csv file in the data folder.
- Calculates and colors a recommended weight range based off BMI.
  - BMI is NOT a great indicator of health, but it's a starting place.
  - The minimum BMI value is 18.5 and the max is 23.9.
- Goals are plotted as a fixed line.
- Plot size is set by the targets 'start_date' and 'weeks'.
- Plot height automatically adjusts it's y-scale to fit weight and recommended weight range.
