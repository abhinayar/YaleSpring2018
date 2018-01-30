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



Class 4

01/25/2018

  

Perceptron:

- 1950’s, Frank Rosenblatt (IBM + Cornell) 
- Claimed that the perceptron was a great device to use as a basis for building neural models 
- “Neural Dynamics” 
- From the beginning you get the sense that this is what we’ll be building off of 
  

Minsky + Papert: Perceptrons

- Emphasized not WHAT perceptrons COULD do but what they could NOT do 
- Two famous examples: 
    - XOR function, Connected predicate 

- Wrote this book because they used it to take the funding from the office of naval research that was going to Rosenblatt, and re-assign it to the AI lab at MIT 
- Perceptrons != AI (succeeded for 10-20 years) was their argument 
- Pushed towards LISP/symbolic rewriting and away from neural nets 
  

Now we read about how neural networks and AI may or may not be the same.

AI is now synonymous with Deep learning -&gt; Networked layers of neurons

  

Last week we had a linear unit with:

- A number of inputs 
- A number of weights 
- Do some math on the above two, run it through a LINEARITY (activation function), and then map to some output (binary output = binary classification) 
    - Many forms for activation function: Sigmoid, Sine, Hyperbolic tangent 

  

Data given is PAIRS in binary classification with supervision problem:

- Input + class pair 
    - Ex: (Face1, Male), (Face2, Female), etc. 

- We want a set of weights W, such that W * X (inputs) = Y for all i in the domain 
  

Classification problem is a problem of dividing the input domain with a linear HYPERplane (b c high dimensional data)

- Affine sets 
- Linear hyperplanes 
- Half Space 
  

Solution is an affine set, which is given by W * X + bias = 0

- Bias is to adjust for error, OFFSET of hyperplane through 0 
- We can feed this bias into the perceptron as another input 
  

Suppose domain is LINEARLY SEPERABLE (sometimes it is not, then we have to use support vectors to push to higher dimension and see if the higher dimension is seperable)

- Going over Rosenblatt’s Precerptron learning algo. 
  

If data is linearly seperable, then the perceptron learning algorithm, PROVABLY converges in a finite # of steps

- However the finite # may be larger than the number of data points that you have 
- You may have to cycle through the data MULTIPLE times before you get convergence 
- K nearest neighbors, PLA (both algorithms to look into) 
- IF data space is NOT linearly seperable, there will be no convergence 
  

Where do you start in the data points?

- You average the +1’s and -1’s in the input data set to start somewhat intelligently 
  

What’s the “margin”?

- Key point in deep learning 
- Suppose data points are dist. In a weird way...  
    - The CLOSER the data points are clustered, the harder time the Perceptron learning algo has 
    - The further away the easier to draw a dividing hyperplane 
    - Margin(D, w, w0) = { min(x,y in D) y(wX + w0) if w seperated D, OR -inf.) 

- Margin for the entire data set (written GAMMA) is going to be the SUP(w,w0) of the margin(D, w, w0) 
  

Perceptron convergence theorem:

- Suppose PLA (perceptron learning alg) is run on seperable data D, with margin GAMMA with is +, and the data are normalized (|| X || &lt; 1, norm &lt; 1, BOUNDED BALL OF DATA), x in D 
- Then the algorithm converges at MOST 1/GAMMA^2 updates 
  

Two influential examples from Cognitive Science and viewing this as a basis for all cognitive styles of thinking. 

- Goes back to the people who thought you could write everything in logic 
- Interesting to think of logical AND function: 
    - Takes pair of BOOLEAN variables and classifies 
    - 0/1 look like classes 

- XOR doesn’t have clear decision boundary, thus is what DIRECTLY led to deep networks (look into this) 
  

How do you apply all this to vision?

- One: let’s think of a diameter limited perceptron: 
    - Meaning each perceptron only sees some of the data but not all of the data 
    - As if you’re only looking at a part of the image and on the basis of that you have to go +/- 1 

- Question is if you can calc. All these disseperate values and come up with some truth about the image 
    - With single layer perceptron is difficult, Minsky proved you cant solve some topological tyle geometric problems that you cant solve with any diameter limited perceptron device 
    - Mathematically what’s key is that connectivity is a GLOBAL property, hard to solve with local measurements

--

## Class 5 - 01/30/2018

Bayes Rule

p(ci, x) = joint prob. of seeing a feature of pattern X, drawn from class i
 
= p(x | ci)*p(ci) / Sum(i)(p(x | ci)*p(ci))

Basically potential = likelihood x prior / evidence

**Decision Rule**
- Decide c1 if p(x|c1)p(c1) > p(x | c2) * p(c2)
- Minimized p(error)
- p(error | x) = EITHER: p(c1 | x) if decide c2, OR p(c2 | x) if c1
- p(error) = -inf -> inf Integral(p(error | x) p(x) dx)

**Bayes Classifier**

- Minimize average risk
- Cost of taking action based on a decision
- Two classes: C1, C2
	- The prior probability p_i, is the prob. that obs. X is drawn from Ci
	- Prior probability is your belief/prob. estimate WITHOUT seeing what happened in real life in the data
- p1 + p2 = 1
- C_ij is the COST of deciding class Ci when the actual true class is Cj
- Terms:
	- Sigma Algebra
	- Barrell field
	- Fuzzy math

**Pretend 2 class classific. problem- both gaussians**
- Something... slept

**Bayes Classifier For Gaussian Dist. (Only means differ)**

p(x | ci) = 1/(2pi)^(m/2) (dc + c)^(1/2) exp(1/2(x_bar - mean_i)^transpose * Cov. matrix ^ -1 * 

Some other shit...
- Go over Bayes Classifier
- Stochastic probabilities
- Other key terms in this lecture








