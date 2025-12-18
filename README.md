

README — Interactive Bézier Curve with Physics & Sensor Control

Overview
This project implements an interactive cubic Bézier curve that behaves like a springy rope. The curve responds in real time to user input (mouse on Web or gyroscope on iOS) and visualizes both the curve and its tangents.

Math (Bézier Curve)
The curve is a cubic Bézier defined by four control points .
The curve is computed using the standard equation:
,
where .
The curve is sampled at small intervals (e.g., 0.01) to render a smooth path.

Tangent Computation
Tangents are calculated using the analytical derivative of the Bézier equation:
.
Each tangent vector is normalized and drawn as a short line segment along the curve.

Physics Model
To create smooth, natural motion, control points  and  follow a spring–damping model:
acceleration = -k * (position - target) - damping * velocity.
Velocity and position are updated every frame, producing elastic, rope-like behavior.

Interaction Design

Endpoints  and  are fixed.

Middle control points respond to input (mouse movement on Web or gyroscope data on iOS).

Rendering runs in a continuous animation loop to maintain ~60 FPS.


Design Choices

All math and physics are implemented manually (no Bézier or physics libraries).

Code is organized into clear sections: math, physics, input handling, and rendering.

Simple visuals (points, curve, tangents) are used to clearly demonstrate the underlying concepts.

How to Run (VS Code)
 Open the project folder in VS Code
 Open Simple-brezier.html 2
 Right-click inside the file and select "Open with Live Server" (or simply open the file in a browser)
Move the mouse to interact with the Bézier curve
