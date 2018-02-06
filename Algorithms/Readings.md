# Preface
- Algorithmic ideas are pervasive and their reach is apparent in CS and beyond
- Internet routing algos are shortest path algos
- Similarities between genes have algorithmic answers
- Serving ads to users = Network Flow problem
- Clean solutions to messy problems

# Chapter 1
## Introduction: Some Representative Problems

**Stable Matching Problem**
- The Problem:
  - 1962 origins, Gale + Shapley = mathematical economists
  - Could one design a college admission/job recruitment process that was SELF ENFORCING
  - Think about juniors applying for internships:
    - You have *employers* and *applicants*
    - Each applicant has preference order
    - Each company has preference for applicants
    - Companies offer to their prefferred candidate but WHAT CAN GO WRONG?
  - Companies may begin fighting for applicants and applicants may leave Companies
    - If you get a better offer from another co. for example, you leaving could disrupt the whole chain
  - Problem: NOT SELF ENFORCING. If people are allowed to act in self interest the whole thing breaks down
- Problem Statement Formal:
  - Given a set of preferences amongst employers and applicant, can we assign applicants to employers so that for every employer E, and applicant A, at least one of the following is true:
    1. E preferes every one of it's accepted applicants A
    2. OR A prefers her current situation over working for employer E
  - If this holds, outcome is STABLE
- FORMULATING THE PROBLEM:
  - Make problem clean as possible
  - Bare bones version:
    - n applicants apply to n co's
    - each co. accept ONE app.
  - We can make it a GENDER problem, match *m* men with *m* women so that all preferences align or at least no one wants better than what they have
    - *MATCHING*: A matching is a set of ordered pairs, each from M x W, with prop that each member of M and each member of W appears in AT MOST one pair in S
    - *PERFECT MATCHING*: A perfect matching is a matching with prop that each member of M and W appear in EXACTLY one pair in S
  - In a perfect matching, if any 2 members of different pairs prefer each other more than their partners then there will be an INSTABILITY
  - Instances may have more than one stable matching
- DESIGNING THE ALGO:
  - Gale-Shapley algorithm
  - Add free, engaged and final states
    - Init. all free
    - Free man m, proposes to free woman w, then rest go and if w prefers m' to m, m is freed and w and m' are engaged and m goes to start proposing again till everyone is engaged.
  - G-S algo is simple to state but this does not prove it's robustness
- ANALYZING THE ALGO:
  - We see that: w remains engaged from the point she receives first proposal and then the sequence of partners to which she is engaged gets better and better
  - Sequence for MEN on the other hand, get's worse and worse. They propose to women further and further down their preference list as they find themselves free
  - G-S algo. terminates after MAX(n^2) (O(n^2))
    - Because at most each man can propose to one woman, if there are n of both then n^2 proposals is max.

  **Upper Bounding Algo. Time**
  - Useful strat. for algo. runtime upperbound is find a measure of *PROGRESS*
  - Some precise way of saying that EACH STEP taken brings closer to term.
    - For this one, each step is some man proposing to some woman he has NOT proposed to before P(t)
    - P(t+1) is > P(t) (STRICTLY)
    - But P(.) is bounded at n^2
    - Make sure you pick a quantity that is STRICLTY increasing over time steps

  **Proving that G-S Algo Returns Perfect Matching**
  - No man can "fall off" the end of his preference list, only way for the algo to exit is there is NO free man
  - If there is no free man then by def must be perfect matching

  **Extensions**
  - There is an unfairness to the G-S algo in that it favors the party that is proposing
  - Question: *Do all executions of the G-S algo. return the same matching?*
    - Answer: All executions yield the same matching, we will explore why

  **All Execution of G-S Yield Same Matching**
  - # of ways to prove
  - Easiest is to uniquely char. the matching that is obtained and show that all executions result in this char.
    - Q: What does it mean to characterize a matching?
    - Q: How do you show that a matching exhibits the character?
  - Characterization: We show that each man ends up with the "best possible partner" in a concrete insensitive  
    - 1. We say woman *w* is a *valid partner* of m if there is a stable matching that contains (m, w)
    - 2. We say woman *w* is *best valid partner* of m if w is a valid partner of m and no woman whom m ranks higher than w is a valid partner of his
    - *best valid partner* = best(m)
  - Let S* represent set: {(m, best(m)), m elem. of M}
    - We prove: Every exec. G-S results in S*
      - Proof by contradiction
      - Long proof, basically you have an execution E where a man m is REJECTED for the first time by woman w in favor of current engagement to m' or breaks engagement with m.

        Means w prefers m' over m. But since this is first rejection means w is best(m). Since w is best(m), then (m, w) is in a stable matching S'

        But who is m' paired with in S'? Clearly since in execution E, (m', w) was a pair and men propose in decreasing order of preference and w rejecting m was the FIRST rejection, any pair of m' in S' other than (m', w) is an instability since w rejected m before for m', thus (m', w) is na instability.

        Convoluted way of saying basically men always get their ideal spouse, women get worst valid partner. Basically side that DOES the proposing gets best possible partner, while side being proposed to gets worse.

**Five Rep. Problems**
- Stable matching gives good example of process of algo. design
- Few sig. steps:
  1. Forumulating problem with enough mathematical precision that we can ask a concrete question and think of algo's
  2. Designing an algo. for the problem
  3. Analyzing the algo. by proving it is correct and giving a bound on the running time to establish the algo. efficacy
- Few fundamental design techniques
  - We will explore these
- We will use graphs
  - Encode pairwise relationships
- Now look at rep. problems:
  1. Interval Scheduling
    - You have a resouce and many people request to use it for periods of time
    - A request is of form: "CAN I RESERVE THE RESOURCE FROM TIME S TO TIME F?"
    - Scheduler wants to accept a subset of requests and reject all others so that requests dont overlap in time
    - Goal is to MAX the # of requests accepted
    - We can solve this using the GREEDY SORT algo.
      - Greedy algo. are MYOPIC rules that process input one piece at a time with no look ahead
  2. Weighted Interval Scheduling
    - With reg. interval scheduling we wanted to max. # of requests served
    - With weighted, each request has a value/weight
    - Goal is to find a subset of intervals that maximize total value
    - No simple greedy rule for this, algo. must be sensitive to values and degenerate ot greedy when all vals. are 1
      - We employ DYNAMIC programming that builds up the optimal value over all possible solutions in a compact tabular way
  3. Bipartite Matching
    - Bipartite graph: Any graph whose node set V can be partitioned into sets X and Y in such a sway that every edge has one end in X and the other end in Y.
    - Matchings in bipartite graphs can model situations in which objects are being ASSIGNED to other objects.
      - Nodes can rep relationships, jobs, etc.
    - Bipartite Matching Problem: Given an arbit. bipartite graph, find a matching of max. size. If |X| == |Y| == n, then there is a perfect matching iff. the max. matching has size n.
    - Solved using *AUGMENTATION* and forms entral component in *NETWORK FLOW PROBLEMS*
  4. Independent Set
    - Ind. Set Problem: Given graph G, find an indp. set that is AS LARGE as possible.
      - Indp. set == set of nodes S is indp. if no two nodes in S are joined by an edge.
    - Encodes any situation where you are trying to choose from a collection of objects and there are pairwise conflicts amongst some objects
    - Interval Sched. and Bipartite Matching are special cases of indp. set problem
    - No efficient alg. known for problem, conjectured that none exist.
      - BUT can easily check the validity of the answer. Kind of like verifying a hash vs. solving a hash???
  5. Competitive Facility Location
    - PSpace Complete Problems
    - Can't find solution or verify solution easily
