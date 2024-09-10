# R-Program-for-Data-Manipulation-and-Visualization

Key Functionalities:
dplyr:

filter(): Filters rows based on a condition.
select(): Selects specific columns.
mutate(): Creates a new column.
ggplot2:

geom_point(): Creates a scatter plot.
geom_bar(): Creates a bar plot.
tidyr:

gather(): Reshapes wide format data into long format.
spread(): Converts long data back to wide format.
lubridate:

ymd(): Converts string to date.
year(), month(), day(): Extract date components.
now(): Returns the current date and time.
stringr:

str_length(): Finds string length.
str_sub(): Extracts a substring.
str_replace(): Replaces text in a string.
str_split(): Splits strings.


# program
# Load necessary libraries
library(dplyr)      # For data manipulation
library(ggplot2)    # For data visualization
library(tidyr)      # For reshaping data
library(lubridate)  # For handling date/time
library(stringr)    # For string manipulation

# 1. Data Manipulation with dplyr
data(mtcars)  # Load built-in mtcars dataset

# Filter rows where mpg is greater than 20
filtered_data <- mtcars %>% filter(mpg > 20)
print("Filtered Data (mpg > 20):")
print(filtered_data)

# Select only the columns mpg and wt
selected_data <- mtcars %>% select(mpg, wt)
print("Selected Columns (mpg, wt):")
print(selected_data)

# Add a new column converting wt from 1000 lbs to kilograms
mtcars <- mtcars %>% mutate(weight_kg = wt * 453.592)
print("New Column (weight in kg):")
print(head(mtcars))

# 2. Data Visualization with ggplot2
# Scatter plot of wt vs mpg
ggplot(mtcars, aes(x = wt, y = mpg)) + 
  geom_point(colour = "blue", size = 3) + 
  ggtitle("Scatter Plot of Weight vs MPG") +
  xlab("Weight (1000 lbs)") + 
  ylab("Miles per Gallon")

# Bar plot of cylinder counts
ggplot(mtcars, aes(x = factor(cyl))) + 
  geom_bar(fill = "green") + 
  ggtitle("Bar Plot of Cylinder Counts") + 
  xlab("Number of Cylinders") + 
  ylab("Frequency")

# 3. Data Reshaping with tidyr
# Convert wide data to long format (gather)
long_data <- mtcars %>% gather(key = "measurement", value = "value", mpg, wt)
print("Long Data Format:")
print(head(long_data))

# Convert long data back to wide format (spread)
wide_data <- long_data %>% spread(key = "measurement", value = "value")
print("Wide Data Format:")
print(head(wide_data))

# 4. Date Manipulation with lubridate
# Create a date using ymd() function
date <- ymd("2023-09-01")
print("Date:")
print(date)

# Extract year, month, and day from the date
year_value <- year(date)
month_value <- month(date)
day_value <- day(date)
print(paste("Year:", year_value, "Month:", month_value, "Day:", day_value))

# Get current date and time using now()
current_time <- now()
print("Current Date and Time:")
print(current_time)

# 5. String Manipulation with stringr
# Calculate the length of a string
string_length <- str_length("R Programming")
print(paste("Length of 'R Programming':", string_length))




read_csv(): Reads data from CSV files (commented out).
write_csv(): Writes data to CSV files (commented out).

