# BubbleSketch

Recent years have witnessed the important role of sketches in identifying heavy
items (e.g., heavy hitters, Top-k items, and persistent items) within large-scale
data streams. However, prior efforts are often compromised in either processing
performance or accuracy, falling short of optimizing the performance-accuracy
trade-off to cope with the ever-increasing data volume within limited memory
resources. Furthermore, ensuring invertibility for heavy item detection in one-
pass data streams is essential, as it allows heavy items to be returned directly
from the sketch without traversing the original data stream. Our aim in this
work is to design a compact and invertible algorithm that is friendly to various
heavy item detection tasks, called Bubble Sketch, which achieves high perfor-
mance and accuracy. The core idea of Bubble Sketch is twofold: (1) Only record
the full keys of real heavy items within the data structure, ensuring invertibility
while greatly reducing memory usage. (2) When conflicts occur between potential
heavy items, use the “threshold relocation” method to resolve them, thereby sub-
stantially enhancing detection accuracy. Through the above two points, Bubble
Sketch can maintain high accuracy levels with invertibility and utilize a min-
imal memory footprint. In addition, since Bubble Sketch does not rely on an
auxiliary Min-Heap like other conventional heavy item detection algorithms, and
each insertion only requires a small amount of entry sorting and replacement in
a bucket, its processing speed is remarkably fast. Extensive experimental results
demonstrate that Bubble Sketch achieves unparalleled accuracy and throughput
in both heavy hitter and Top-k item detection tasks, while outperforming most
comparison sketches and showing competitive performance with the state-of-the-
art specialized sketch in persistent item detection, especially for small memory
environments.

# How to run

Suppose you've already cloned the repository.

You just need:

```
$ make
$ ./BubbleSketch (-d dataset -m memory -k k)
```

**optional** arguments:

- -d: set the path of dataset to run, default dataset is CAIDA "1.dat"
- -m: set the memory size (KB), default memory is 400KB
- -k: set the number of top flows, default **k** is 1000

# Output format

Our program will print the Throughput of insertion, AAE, ARE and Precision of these algorithms on the screen.
