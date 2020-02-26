# Bezier-Curve

A ROBLOX module script for creating bezier curves. This is optimized automatically for both the quadratic case if 3 points are given, and the cubic case if 4 points are given. Can handle an unlimited number of points.

## Methods:
```Lua
local Bezier = require(thisModule)
b = Bezier.new(Vector3 pointA, Vector3 pointB, Vector3 pointC, ...)
	-- Must input at least 3 Vector3 points, or else it will throw an error

Vector3          b:Get(ratio)
	-- Get a Vector3 position on the curve with the given ratio. Ratio should be between 0 and 1, translated to 0% and 100%

Array<Vector3>   b:GetPath(step)
	-- Create path along curve (returns table of Vector3 positions)
	-- 'step' is the ratio step and should be within the range of (0, 1)

Array<Vector3>   b:GetPathBySegmentLength(segmentLength)
	-- Create a path along the curve, where the segments are roughly 'segmentLength' long

Array<Vector3>   b:GetPathByNumberSegments(numSegments)
	-- Creates a path along the curve with 'numSegment' segments

Number           b:GetLength([step])
	-- Returns the length of a given path based on the step
	-- 'step' is the ratio step and should be within the range of (0, 1). It defaults to 0.1
	-- This is the same as calling 'b:GetPath(step)' and then summing up the distances
	  between each point. It is a rough approximation.

Array<Vector3>   b:GetPoints()
	-- Get the original control points that were inputted when object was created
```

More info on Bezier Curves:
	http://en.wikipedia.org/wiki/Bezier_curve
	http://en.wikipedia.org/wiki/De_Casteljau%27s_algorithm

I recommend reading the Properties section for the first Wiki link