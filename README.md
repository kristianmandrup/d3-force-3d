# d3-force-3d

[![NPM](https://nodei.co/npm/d3-force-3d.png?compact=true)](https://nodei.co/npm/d3-force-3d/)

Extended version of [d3-force](https://github.com/d3/d3-force) to support other dimensions besides 2D, via the method [*numDimensions*](#simulation_numDimensions), supporting the values 1, 2 or 3 (default to 2). Fully backwards compatible with [d3-force](https://github.com/d3/d3-force) (version [1.1.0](https://github.com/d3/d3-force/tree/v1.1.0)), and should just work as a drop-in replacement d3 module.

This module implements a [velocity Verlet](https://en.wikipedia.org/wiki/Verlet_integration) numerical integrator for simulating physical forces on particles. The simulation is simplified: it assumes a constant unit time step Δ*t* = 1 for each step, and a constant unit mass *m* = 1 for all particles. As a result, a force *F* acting on a particle is equivalent to a constant acceleration *a* over the time interval Δ*t*, and can be simulated simply by adding to the particle’s velocity, which is then added to the particle’s position.

In the domain of information visualization, physical simulations are useful for studying [networks](http://bl.ocks.org/mbostock/ad70335eeef6d167bc36fd3c04378048) and [hierarchies](http://bl.ocks.org/mbostock/95aa92e2f4e8345aaa55a4a94d41ce37)!

[<img alt="Force Dragging III" src="https://raw.githubusercontent.com/vasturiano/d3-force-3d/master/img/graph.png" width="420" height="219">](http://bl.ocks.org/mbostock/ad70335eeef6d167bc36fd3c04378048)[<img alt="Force-Directed Tree" src="https://raw.githubusercontent.com/vasturiano/d3-force-3d/master/img/tree.png" width="420" height="219">](http://bl.ocks.org/mbostock/95aa92e2f4e8345aaa55a4a94d41ce37)

You can also simulate circles (disks) with collision, such as for [bubble charts](http://www.nytimes.com/interactive/2012/09/06/us/politics/convention-word-counts.html) or [beeswarm plots](http://bl.ocks.org/mbostock/6526445e2b44303eebf21da3b6627320):

[<img alt="Collision Detection" src="https://raw.githubusercontent.com/vasturiano/d3-force-3d/master/img/collide.png" width="420" height="219">](http://bl.ocks.org/mbostock/31ce330646fa8bcb7289ff3b97aab3f5)[<img alt="Beeswarm" src="https://raw.githubusercontent.com/vasturiano/d3-force-3d/master/img/beeswarm.png" width="420" height="219">](http://bl.ocks.org/mbostock/6526445e2b44303eebf21da3b6627320)

You can even use it as a rudimentary physics engine, say to simulate cloth:

[<img alt="Force-Directed Lattice" src="https://raw.githubusercontent.com/vasturiano/d3-force-3d/master/img/lattice.png" width="480" height="250">](http://bl.ocks.org/mbostock/1b64ec067fcfc51e7471d944f51f1611)

With this module update, you can also run the simulation in one, two or three dimensions:

[<img alt="3D Graph" src="https://raw.githubusercontent.com/vasturiano/d3-force-3d/master/img/3dgraph.png" width="480">](https://bl.ocks.org/vasturiano/f59675656258d3f490e9faa40828c0e7)

To use this module, create a [simulation](#simulation) for an array of [nodes](#simulation_nodes), and compose the desired [forces](#simulation_force). Then [listen](#simulation_on) for tick events to render the nodes as they update in your preferred graphics system, such as Canvas, SVG or WebGL.

## Web Examples

Contains a small static web server example demonstrating visualization of *Les Miserables* character connections.

See [Examples.md]() document for run instructions.

### Example code

The miserables example demonstrates how you can write a simple web app that leverages this library.

- `/web/miserables` the web app
- `/web/data` the data visualized
- `/web/lib` the d3-force-3d lib used

Enjoy :)
