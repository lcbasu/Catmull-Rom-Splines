# Catmull Rom Splines

Organized catmull rom spline implementation in Unity.

Spline logic is in its own data structure; Catmull Points (Position, Normal, Tangent) is its own struct.

I cleaned up the code from my Road Generator repository, since that was... best not to mention it.

If you use it anywhere give me a ping on noobstudiosunity @ gmail.com

# Contains

Spline Class:

	CatmullRomPoint { Position, Normal, Tangent }
	Constructor()
	Update(Transform[] ControlPoints)
	Update(Resolution, ClosedLoop)
	DrawSpline(Color)
	DrawNormals(Length, Color)
	DrawTangents(Length, Color)
	Evaluate(p0, p1, m0, m1, t)
	CalculatePosition(p0, p1, m0, m1, t)
	CalculateTangent(p0, p1, m0, m1, t)
	NormalFromTangent(Tangent)

Usage:

```
if(spline != null)
{
	spline.Update(controlPoints);
	spline.Update(resolution, closedLoop);
	spline.DrawSpline(Color.white);

	if(drawNormal)
		spline.DrawNormals(normalExtrusion, Color.red);

	if(drawTangent)
		spline.DrawTangents(tangentExtrusion, Color.cyan);
}
else
{
	spline = new CatmullRom(controlPoints, resolution, closedLoop);
}
```
