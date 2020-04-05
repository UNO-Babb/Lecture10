# Lecture 10 - CYBR 2980

## Data Visualization with Python Libraries
One of the biggest uses of Python is for data analysis and to create charts, graphs, and other visual representations of data.

## Matplotlib
Matplotlib is one of the most popular data visualization tools in Python. We see it used in different ways in different contexts, often you will see people using this as part of a Jupyter Notebook.

First we need to install Matplotlib on your computer. At the command prompt you will need to type the following commands:
```
python -m pip install -U pip
python -m pip install -U matplotlib
```

For our first example, we can plot a straight line.
```
import matplotlib.pyplot as plt
plt.plot([1, 2, 3, 4])
plt.ylabel('some numbers')
plt.show()
```

We can also change the plot line to graph X values against Y values.
```
plt.plot([1, 2, 3, 4], [1, 4, 9, 16])
plt.show()
```

Another useful feature is setting the scale of the axis as well as determining the style of the plot.
```
plt.plot([1, 2, 3, 4], [1, 4, 9, 16], 'ro')
plt.axis([0, 6, 0, 20])
plt.show()
```
If matplotlib were limited to working with lists, it would be fairly useless for numeric processing. Generally, you will use **numpy** arrays. In fact, all sequences are converted to numpy arrays internally. The example below illustrates plotting several lines with different format styles in one command using arrays.

```
import numpy as np

# evenly sampled time at 200ms intervals
t = np.arange(0., 5., 0.2)

# red dashes, blue squares and green triangles
plt.plot(t, t, 'r--', t, t**2, 'bs', t, t**3, 'g^')
plt.show()
```
Finally, for this discussion, we can use random data to show how data might be visualized.
```
data = {'a': np.arange(50),
        'c': np.random.randint(0, 50, 50),
        'd': np.random.randn(50)}
data['b'] = data['a'] + 10 * np.random.randn(50)
data['d'] = np.abs(data['d']) * 100

plt.scatter('a', 'b', c='c', s='d', data=data)
plt.xlabel('entry a')
plt.ylabel('entry b')
plt.show()
```

### Further Exploration
Work through some of the examples on the Matplotlib website to see how other graphs, charts, and visualizations can be constructed.
[Matplotlib Examples Site](https://matplotlib.org/gallery/index.html)


## Pandas
Pandas is a powerful data tool that uses Matplotlib for visualizations. This tool will allow us the take large datasets in common formats (SQL, CSV, JSON, etc.) and allow us to do processing and manipulation of the data. We can then save the modified data or create visuals.

**Install Pandas**
```
python -m pip install -U pandas
```

Now that we have Pandas installed, we can start to load data into the pandas format.
```
import pandas as pd

df = pd.DataFrame({"Name": ["Braund, Mr. Owen Harris",
  "Allen, Mr. William Henry",
  "Bonnell, Miss. Elizabeth"],
  "Age": [22, 35, 58],
  "Sex": ["male", "male", "female"]})

print(df)
```

We can also break out some details of the data if that is all we are interested in.
```
print(df["Age"])
```

We can also do analysis on a subset of the data.
```
print(df["Age"].max())
```
or even
```
print(df.describe())
```

### Further Exploration
[Pandas Getting Started Guide](https://pandas.pydata.org/docs/getting_started/10min.html)

### Resources:
[Matpotlib Website](https://matplotlib.org/tutorials/index.html)
[Pandas Documentation](https://pandas.pydata.org/docs/index.html)
