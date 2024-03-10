Given plane in 3D space, defined by 3 points 
$$
a_{1}, a_{2}, a_{3}
$$
[[Normal Vector]] $\nu$ can be calculated:
$$
\nu = (a_{1} - a_{3}) \times (a_{2}-a_{3})
$$
Where $\times$ is [[Cross Product]].

Then distance from vector to plane is:
$$
D = \nu  \cdot a_{1}
$$
$$
ax + by + cz = d
$$

Where `a`, `b`, and `c` are the coefficients of the plane's normal vector, and `(x, y, z)` are the coordinates of any point on the plane. `d` is the distance from the origin to the plane along the normal vector.

$$
P(t) = P0 + tV0
$$

Where:

- `P(t)` is a point on the line for parameter `t`.
- `P0` is the starting point of the line (camera coordinates).
- `V0` is the direction vector of the line (the vector from the camera to a corner of the FOV rectangle).
- `t` is a scalar parameter.

We solve for `t` such that the point `P(t)` lies on the plane. Substituting `P(t)` into the plane equation, we get:


$$a(P0_x + tV0_x) + b(P0_y + tV0_y) + c(P0_z + tV0_z) = d$$

Solving for `t`, we get:


$$t = \frac{(D - dot(normal, P0))}{dot(normal, V0)}$$
    
    Once we have `t`, we substitute it back into the parametric equation to find the intersection point `P(t)`.




# Code:
```python
def find_intersection_points(self, vectors: List[np.ndarray]) -> List[np.ndarray]:  
    """  
    Find the intersection points of the FOV rectangle vectors with a given plane.  
    :param vectors: Vectors from camera to corners.    :return: List of intersection points.    """    intersection_points = []  
  
    a1, a2, a3 = self.plane[0], self.plane[1], self.plane[2]  
    normal = np.cross(np.array(a2) - np.array(a1), np.array(a3) - np.array(a1))  
    D = np.dot(normal, np.array(a1))  
  
  
    for vector in vectors:  
        p0 = np.array(self.camera_coords)  
        v0 = np.array(vector)  
  
        t = (D - np.dot(normal, p0)) / np.dot(normal, v0)  
        intersection_point = p0 + t * v0  
  
        if t < 0 or self.DEBUG_SHOW_ALL_LINES:  
            intersection_points.append(intersection_point)  
  
    return intersection_points
```