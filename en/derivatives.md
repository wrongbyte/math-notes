The easiest way to understand what a derivative is is by using velocity. When we say the velocity of something is 100m/sec, it is actually the _average_ velocity. The derivative lets us discover the **instantaneous** velocity.

This is useful when the velocity varies; for example, when driving a car in a city, the velocity is sometimes faster and sometimes slower. If you draw a graph with axes t (time) and s(space), the derivative of this graph is the velocity.
![image](https://github.com/user-attachments/assets/533a7310-e55c-4a0a-b050-681bce2f2c4c)

The derivative is easier visualized as the slope of the line tangent to a point in a curve, just like the image above. However, we are not exactly dealing with a "point", but to an infinitely small amount of t and s. 

### Increments method
Formally, the derivative is the rate of change of a function when that change approaches zero. In a function, it can be defined as it follows:

![image](https://github.com/user-attachments/assets/19252b39-f67a-4ddb-b88e-e7b70c4fe182)

With this definition in mind, we can find interesting results. For example, think about the area of a circle. It is given by
```math
A = \pi r^2
```
In this formula, $r$ is the independent variable, and the area is the dependent variable - which is, the value of area depends on the value of $r$. **How much the area of a circle increases as the radius increases?**

To find the answer of this question, we can invoke the definition of a derivative, since it is the rate of a function when **the change in independent variable tends to zero**.
We can define the change in $r$ by $\Delta r$. Thus, the new radius becomes
```math
r + \Delta r
```

Since we increased the value of our radius, the new area of the circle becomes 
```math
A_{\text{new}} = \pi (r + \Delta r)^2
```
And the process goes:
```math
A_{\text{new}} = \pi \left( r^2 + 2r\Delta r + (\Delta r)^2 \right)
```

As $r$ changes, $A$ also changes. We can get $\Delta A$ using
```math
\Delta A = A_{\text{new}} - A
```
and therefore
``` math
\Delta A = \pi \left( r^2 + 2r\Delta r + (\Delta r)^2 \right) - \pi r^2
```

```math
\Delta A = \pi \left( 2r\Delta r + (\Delta r)^2 \right)
```

```math
\Delta A \approx \pi (2r\Delta r)
```

```math
\frac{\Delta A}{\Delta r} \approx 2\pi r
```

We then get
```math
\frac{dA}{dr} = 2\pi r
```

which is the formula of the circumference.
