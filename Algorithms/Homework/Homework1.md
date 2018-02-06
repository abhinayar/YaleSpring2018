# Problem Set 1 - Makeup Pset
## Problems 1, 2 and 4 in Textbook

1. Decide whether you think the following statement is true or false. If it is true, give a short explanation. If it is false, give a counterexample.

  *True or false? In every instance of the Stable Matching Problem, there is a
  stable matching containing a pair (m, w) such that m is ranked first on the
  preference list of w and w is ranked first on the preference list of m.*

  False by counterexample.

  We take a scenario with *m, m', w, w'* where the preferences are as follows:

  m:
    1. w
    2. w'

  m':
    1. w'
    2. w

  w:
    1. m'
    2. m

  w':
    1. m
    2. m'


  This is an instance where there is no pair (m,w) such that m is ranked first on preference list of w and w is ranked first on preference list of m. Trick is the wording of the problem which says in *every instance* of the SMP, which is clearly not true because some instances of the SMP just don't have stable matches.

2. Decide whether you think the following statement is true or false. If it is true, give a short explanation. If it is false, give a counterexample.

  *True or false? Consider an instance of the Stable Matching Problem in which
  there exists a man m and a woman w such that m is ranked first on the
  preference list of w and w is ranked first on the preference list of m. Then in
  every stable matching S for this instance, the pair (m, w) belongs to S.*


  I believe this is true. There will always be a Stable Matching, S, containing *(m, w)*. In the scenario with two men (*m, m'*) and two women (*w, w'*) where *m* and *w* have each other at the top of their preference list, if a stable match S' contained *(m', w)* or *(m, w')* there would be an instability because *m* would strictly prefer *w* while *w* would (at the same time) strictly prefer *m*, thus contradicting the claim that S' is a stable match.

  Therefore the statement is true and in every stable matching S the pair *(m, w)* will belong to S.

4. [Some background on problem]. Show that there is always a stable assignment of
    students to hospitals, and give an algorithm to find one.

    Conditions:
      - hospitals generally want more than one resident
      - there is a surplus of medical students

    Solution:
    - Let R be the set of residents, H be the set of hospitals, and let a hospital be free if it has at least one empty slot available.
    - Initially all r ∈ R and h ∈ H are free
      - While there is a hospital h who is free and hasn't proposed to every resident r
        - Choose such a hospital h
        - Let r be the highest-ranked resident in h’s preference list to which h has not yet proposed
        - If r is free then (h, r) become engaged
        - Else r is currently engaged to h'
          - If r prefers h' to h then
            - h remains free
          - Else r prefers h to h'
            - (h, r) become engaged and h's open slots decrease by 1
            - h' becomes free (open slots increase by 1)
          - Endif
        - Endif
      - Endwhile
      - Return the set S of engaged pairs of residents and hospitals
