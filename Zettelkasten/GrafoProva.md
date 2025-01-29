```graph
bounds: [-2, 2, 2, -2]
keepAspectRatio: true
elements: [
	{type: implicitcurve, def: ["f:x+y*y-1"]},
	{type: functiongraph, def: ["f:-x+1.25"]},
	{type: functiongraph, def: ["f:-x"], att: {name: "$y=-x+k$", withlabel: "true"}},
	{type: point, def: [0.625,0.625]}
]
```
