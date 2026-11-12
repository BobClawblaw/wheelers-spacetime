# Wheeler's Spacetime

> Matter tells spacetime how to curve; curved spacetime tells matter how to move. (John Archibald Wheeler)

An interactive WebGL animation of general relativity around a single mass. Every path is integrated from the
Schwarzschild geodesic equation, so the precessing orbit, the bent light and the slow clocks are computed, not
drawn by hand.

**View it:** https://bobclawblaw.github.io/wheelers-spacetime/

## The three views

- **Curved space.** One instant of space, lifted into an extra dimension to show its curvature (Flamm's
  paraboloid, depth drawn 1.5x). A planet orbits between r = 12 and r = 30 and its perihelion advances each orbit;
  the dashed line is Newton's closed ellipse with the same turning points. Light pulses bend round the mass, and
  rays inside the critical impact parameter 3√3 M are captured.
- **Spacetime (x, y, t).** One space dimension dropped, time running upward. The planet's world line is a helix;
  beads mark equal intervals of proper time on the planet and on clocks held at r = 4, 8 and 30, so the clocks
  deep in the well visibly tick less often. Light cones on the current slice narrow near the mass (radial
  coordinate light speed 1 − 2M/r, tangential √(1 − 2M/r); drawn 15x narrower than the time axis would give).
- **Gravitational waves.** A binary inspirals and merges. The ripple height is the strain at twice the orbital
  frequency, travelling outward at a fixed speed and hugely exaggerated; a face-on ring of free particles shows
  the stretch-and-squeeze of the wave.

Controls: mass M, playback speed, Newton's ellipse on or off; drag to orbit the camera, scroll or pinch to zoom.

## The physics

Units are G = c = 1, lengths in GM/c² (1.48 km for the Sun) and times in GM/c³ (4.9 μs for the Sun).

- Time-like orbits: u'' = M/L² − u + 3Mu² with u = 1/r, integrated with RK4 in the orbital angle, plus
  dt/dφ = E / (L u² (1 − 2Mu)) and dτ/dφ = 1 / (L u²). L and E are set from the periapsis and apoapsis.
- Light: u'' = −u + 3Mu², dt/dφ = 1 / (b u² (1 − 2Mu)).
- Static clocks run at dτ/dt = √(1 − 2M/r).

The readouts compare the measured perihelion advance and light deflection with the weak-field formulas 6πM/p and
4M/b. The orbit sits far deeper in the field than Mercury's, so the measured values exceed the weak-field ones.
The gravitational-wave view is a qualitative quadrupole picture, not a numerical-relativity waveform.

## Running it

It is one static file, `index.html`, loading three.js r128 from jsDelivr and fonts from Google Fonts. Open it in
a browser or serve the folder with any static server.

Inspired by a post from [@PhilosophyOfPhy](https://x.com/PhilosophyOfPhy/status/2120778156407742505).
