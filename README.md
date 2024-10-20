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
```



for bit in stream[::-1]:
    add_bit(bit)

print("Approximate count of 1s in the last 10 bits:", count_ones())
