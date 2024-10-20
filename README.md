# BDA-Prac
This is just a demo repository to study Git and Github


```
buckets = []
current_time = 0
N = 10

def add_bit(bit):
    global current_time, buckets
    current_time += 1


    buckets = [bucket for bucket in buckets if bucket[1] > current_time - N]


    if bit == 1:
        buckets.append((1, current_time))

        while len(buckets) >= 3 and buckets[-1][0] == buckets[-2][0] == buckets[-3][0]:
            new_bucket = (buckets[-1][0] * 2, buckets[-2][1])
            buckets = buckets[:-2]
            buckets.append(new_bucket)

def count_ones():
    global buckets
    total_ones = 0


    for i in range(len(buckets) - 1):
        total_ones += buckets[i][0]


    if len(buckets) > 0:
        total_ones += buckets[-1][0] // 2

    return total_ones


stream = [1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0]




for bit in stream[::-1]:
    add_bit(bit)

print("Approximate count of 1s in the last 10 bits:", count_ones())
```

```
#data visualization in r

install.packages("ggplot2")

# Load the ggplot2 package
library(ggplot2)

# Create a sample dataset
data <- data.frame(
  Category = c("A", "B", "C", "D", "E"),
  Values = c(23, 45, 12, 67, 34)
)

# Create a bar plot
ggplot(data, aes(x = Category, y = Values, fill = Category)) +
  geom_bar(stat = "identity") +
  labs(title = "Bar Plot of Categories", x = "Category", y = "Values")

# Creating a time series dataset
time_data <- data.frame(
  Time = seq(1, 10),
  Measurement = c(5, 7, 8, 10, 15, 20, 25, 30, 28, 35)
)

# Line plot
ggplot(time_data, aes(x = Time, y = Measurement)) +
  geom_line(color = "blue") +
  geom_point() +
  labs(title = "Time Series Data", x = "Time", y = "Measurement")
```
