# 4-Point Coupler Curve Synthesis

An interactive, single-file HTML tool for graphically synthesizing a four-bar linkage whose coupler point passes through four user-specified precision points (C1–C4), using the classic point-position reduction method.

Everything — geometry engine, canvas rendering, and UI — lives in one self-contained synthesis.html file. No build step, no dependencies.

Demo

Just open synthesis.html in any modern browser.

What it does

Given four target points (C1, C2, C3, C4) that you want a coupler point to trace, this tool:


Lets you place two auxiliary construction points (Hr and A1) by dragging blue dots on the canvas.
Uses point-position reduction to derive the fixed pivots and moving pivots of a four-bar linkage (crank, coupler, rocker, and ground link) that guides the coupler point through all four precision points.
Solves for a third auxiliary center (Hc) that fixes the crank pivot circle.
Draws the full construction (circles, intersections, and derived hinge points) so you can see how the synthesis works, not just the result.
Reports the resulting link lengths and flags common linkage defects.
Animates the mechanism so you can watch the coupler point trace its curve through a full crank rotation.


Features


Editable precision points — type in exact (x, y) coordinates for C1–C4.
Draggable construction points — drag Hr, A1, and Hc directly on the canvas to explore the solution space in real time.
Construction line toggle — show or hide the auxiliary circles and points used to derive the mechanism.
Branch selection — swap between the two possible circle-intersection solutions for A2 and A4 when the synthesis is not unique.
Live diagnostics, reported after every change:

Grashof condition (Grashof / Non-Grashof, and whether it's a valid crank-rocker)
Branch defect — whether the mechanism can reach all four points without disassembly/flipping
Order defect — whether the coupler point traces the points in the correct sequence
Computed link lengths (ground, crank, coupler, rocker)



Animation — play/pause a continuous crank rotation to watch the coupler curve traced live.


Usage


Open synthesis.html in a browser.
Adjust the C1–C4 coordinate fields to set your four target (precision) points, or leave the defaults.
Drag the blue dots (Hr, A1, Hc) on the canvas to change the synthesis solution.
Toggle Show Construction Lines to inspect or hide the underlying geometric construction.
Toggle Swap A2/A4 Branch if the solver picks the wrong circle-intersection branch for your case.
Click Play Animation to animate the linkage through a full rotation of the crank.
Watch the status line for Grashof classification and any branch/order defects, and read off the resulting link lengths.


Background

Four-point coupler curve synthesis is a classical problem in mechanism design: given four points that a coupler link should pass through in sequence, find a four-bar linkage (ground link, crank, coupler, rocker) that produces a coupler curve through those points. This tool implements a graphical point-position reduction approach, an alternative to purely analytical (e.g. Freudenstein/Loeb) synthesis methods, and visualizes each construction step interactively.

A resulting mechanism is only practically useful if it is:


Grashof with a crank-rocker configuration (so the input link can fully rotate), and
free of branch defects (reachable without disassembly) and order defects (traces the points in the intended order).


The tool computes and displays all of these automatically as you adjust the design.
