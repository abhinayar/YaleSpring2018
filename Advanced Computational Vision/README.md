01/18/2018

Advanced Comp. Vision

Class 2

—

Today: overview

- Terms:
  - Retina, fovea
  - Lgn
  - Convolution
  - Neuron and it&#39;s parts
  - Food forward, feedback, etc
  - Perceptron
  - Action Potential
  - Supervised vs unsupervised learning
  - Receptive field
  - Orientation selection
  - Filter
  - Least mean squared
  - Stdp (plasticity)
  - Hebbian + higher order learning
  - Mixture models
  - Tensors
  - On line, biological learning
  - Non linear program geometry
  - Parts of visual cortex
    - ■■V1 - V3
    - ■■Lgn
    - ■■Layers (1, 2-3, 4,5)
  - Cliques
  - Hyperacuity
  - Tangential penetration
  - Visual angle, degrees, seconds of vision
  - Tangent bundle
    - ■■All smooth geometric computations
  - Differential geometry
  - Hyper complex cells
  - End stopping

Class 3

01/23/2018

—

Simple view of neuron:

- --Inputs, weights and output
- --Some cost function
  - --Contour detection (filter)
  - --Something else (classifier)
- --Set of weights and inputs = TENSOR
  - --TENSOR-Flow get it
  - --M-dimensional dynamical system
- --We have some error function that is derived from our cost function
  - --Sum of squared errors
  - --We want to minimize the error term

- Unconstrained optimization
  - E = Cost function (weights) [R -&gt; R]
    - ■■We want E(w\*) &lt; E(w)
  - We need the gradient/derivative Grad(E(w\*)) = 0 = [TENSOR OF PARTIAL DER.]
  - Basically we have something to do with an error term here, and a BIG EPSELON (function of w), we want to minimize the error AND Big Epselon
    - ■■Gradient descent
  - Way to optimize for E value?
    - ■■GAUSS-NEWTON OPTIMIZATION
    - ■■How do we go from the Gradient of the cost term (E) to do Gradient descent (we seem to have a NON linear term)

ASIDE #1:

- Newton&#39;s method:
  - In 1D
  - We want to find the roots of f(x), so where y=0
  - Newton&#39;s method takes the derivative and find where the derivative is 0 and that&#39;s an estimate of where the root is
    - ■■Not perfect so we iterate
  - Derivative is also tangent line
    - ■■We use derivative bc the tangent is a GOOD LOCAL approx.
    - ■■Refers back to Taylor&#39;s theorem
  - Taylor&#39;s Method says you can think of the value of y as the derivative evaluated at some point as: y = f&#39;(x\_n)(x-x\_n) + f(x\_n) + error
    - ■■Solve for y = 0, you get x\_n+1 = x\_n - f(x\_n) / f&#39;(x\_n)
  - But how do we extrapolate this to higher dimensions
- Jacobian
  - Matrix of first order partials of vector valued function
  - Scalar functions: Point in plane R2 -&gt; Number R1
    - ■■Gradient of Scalar Function : [df/dx1 df/dx2]
  - Generalizing this scalar function jacobian:
    - ■■F: Rn -&gt; Rn
    - ■■DF = J (Jacobian)
      - J = [dF/dx1 dF/dx2 …. dF/dxn]
      - == [df1/dx1 df1/dx2 … df1/dxn]
      -      [df2/dx1 df2/dx2 … df2/dxn]
      -      [.        .         .         .         .  ]
      -      [dfn/dx1 …..          dfn/dxn]
    - ■■Gauss-Newton uses Jacobian
  - We can also find the Jacobian of errors
    - ■■[d(e1)/dw1 … d(e1)/dwn, … , d(en)/dw1 … d(en)/dwn]
  - Taylor:
    - ■■f(x) = f(x0) + f&#39;(x - x0) + **o** (x - x0)
    - ■■F(X) = F(X0) + J\_F(X0)(X - X0) + **o** || X - X0 ||
      - Second is GENERALIZED to n-dimensions
    - ■■The **o** is the error notation, NOT ZERO
- SO WHY DID WE DO ALL THIS?
  - G-N method is : Non linear least squares for residuals of the form || r(x) || ^2 = SUM (1 -&gt; m) r\_i(x)^2
  - Gauss-Newton method
    - ■■Start with a guess for X
    - ■■Linearize r
    - ■■IN NOTES

Where are we going?

- We have a cost function in weight space (m-dim space)
- We take cost function at a position, linearize it, perform gradient descent, and find the minimal cost function
  - Steps in between are technical and make sense in pictures
  - Game is in high dimensions, cost function of _w_, we want to find the value of w that makes the cost function minimal

GAUSS NEWTON OPTIMIZATION:

- Fix w(n) and linearize it
  - In mathematics, **linearization** is finding the linear approximation to a **function** at a given point. In the study of dynamical systems, **linearization** is a method for assessing the local stability of an equilibrium point of a system of nonlinear differential equations or discrete dynamical systems.
  - SEE ALSO: [https://en.wikipedia.org/wiki/Stability\_theory](https://en.wikipedia.org/wiki/Stability_theory)
- READ ABOUT THIS THIS SHIT IS HARD
- Most of what we cover today:
  - STOCHASTIC definition
  - STOCHASTIC GRADIENT ASCENT definition and application

LINEAR LEAST SQUARES FILTER:

- Single neuron, &quot;full&quot; knowledge
- Moore-penrose Pseudo Inverse
- Basically it &quot;beautifully&quot; lol converges down to a simple case using the Jacobian as the linear approximator

EXAMPLE:

- Pull inputs from random trials
  - Get a number of random variables
  - Ergodic
    - ■■Ergodic theory is a branch of mathematics that studies dynamical systems with an invariant measure and related problems. Its initial development was motivated by problems of statistical physics. [Wikipedia](https://en.wikipedia.org/wiki/Ergodic_theory)
    - ■■Random process is ergodic IF:
      - In econometrics and signal processing, a stochastic **process** is said to be **ergodic if** its statistical
      -
      -
      -
      -
      - properties can be deduced from a single, sufficiently long, **random** sample of the **process**. ... Conversely, a **process** that is not **ergodic** is a **process** that changes erratically at an inconsistent rate.
  - Random stochastic process is like flipping a coin with OMEGA sides, and picking a function where each function is T trials long
  - Ergodic world: TIME averages === Sample averages
  - We need:
    - ■■Correlation matrix of the input = Expec. Value of
- Something about:
  - Wiener filter as n gets large
  - Linear least ma square regression
  - All you need to know to solve mean square problem is 2nd order statistics
- Last version:
  - Instantaneous least mean squares
  - Error(w) = ½\*e(n)^2
  - dError/dw = e(n)\*de(n)/d(w)
  - w\_hat(n+1) = w\_hat(n) + ñ(x\_bar(n) \* e(n))
  - This is called STOCHASTIC GRADIENT DESCENT
  - works in instantaneous values of the data
  - Is a BROWNIAN WALK around the WIENER SOLUTION
