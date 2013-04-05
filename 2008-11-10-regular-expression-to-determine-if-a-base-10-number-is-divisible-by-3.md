---
title: Regular Expression to determine if a base 10 number is divisible by 3
tags: Regular Expressions, Programming
---
I decided to work out the regular expression for matching mod3=0 positive [Decimal (base10)](http://en.wikipedia.org/wiki/Decimal) [Integer](http://en.wikipedia.org/wiki/Integer) today. 
I had a dream about the problem last night (remembering an old lecture) and could not find my notes with the solution (if I even wrote it down). 
So, after googling around for a bit, I gave up, and worked the solution out myself, because it looks like a good void to fill on the interwebs.

##The Problem: 

Let <em>L</em> = { w | w mod 3 = 0 }, where the alphabet is {0,1,2,3,4,5,6,7,8,9}; give the [Deterministic Finite Automaton](http://en.wikipedia.org/wiki/Deterministic_finite-state_machine)(<abbr title="Deterministic Finite Automaton">DFA</abbr>) for <em>L</em>, and convert this to a [Regular Expression](http://en.wikipedia.org/wiki/Regular_expression)

##The Solution (don't peak):

  	<a href="http://erikvold.com/blog/index.cfm/2008/11/10/regular-expression-to-determine-if-a-base-10-number-is-divisible-by-3#more" name="more" rel="nofollow"></a>
		
The <abbr title="Deterministic Finite Automaton">DFA</abbr> ( <i>S</i>, Σ, <i>T</i>, <i>s</i>, <i>A</i> ):<br>
<i>S</i> = {q0,q1,q2}<br>
Σ = {0,1,2,3,4,5,6,7,8,9}<br>
T = (doing the state diagram below)<br>
<i>s</i> = {q0}<br>
<i>A</i> = {q0}

For shorthand I will divide the alphabet, ?, into:

- A={0,3,6,9}
- B={1,4,7}
- C={2,5,8}

The state diagram:
</p><div class="center"><img title="Step 1: DFA State Diagram" alt="DFA State Diagram" src="/blog/images/posts/2008-9-11/dfa-state-diagram.jpg"></div> LINK DOESNT WORK

Now to convert the DFA state diagram into a regular expression. This is done by converting the DFA into [Generalized Nondeterministic Finite Automaton](http://en.wikipedia.org/wiki/GNFA) GNFA, and then converting the GNFA into a regular expression.

<div class="center"><img title="Step 2: Conversion of DFA into GNFA, and removal of q0 state" alt="Conversion of DFA into GNFA, and removal of q0 state" src="/blog/images/posts/2008-9-11/step2.jpg"></div> LINK DOESNT WORK
Notice in the above that I did two steps in one; I first converted the DFA into a GNFA (which is the easy part), then I removed the q0 state.

Removing the q1 state: LINK DOESNT WORK
<div class="center"><img title="Step 3: Removing the q1 state" alt="Removing the q1 state" src="/blog/images/posts/2008-9-11/step3.jpg"></div>

Finally, removing the q2 state: LINK DOESNT WORK
<div class="center"><img title="Step 4: Removing the q2 state" alt="Removing the q2 state" src="/blog/images/posts/2008-9-11/step4.jpg"></div>

Therefore the regular expression that defines the regular language <em>L</em> is:
(A+)∪((B∪A*B)(A∪CA*B)*CA*)∪((C∪A*C∪(B∪A*B)(A∪CA*B)*(B∪CA*C))(A∪BA*C∪(C∪BA*B)(A∪CA*B)*(B∪CA*C))*(BA*∪(C∪BA*B)(A∪CA*B)*CA*))

For further reading please see [Introduction to the Theory of Computation](http://books.google.com/books?id=eRYFAAAACAAJ) by Michael Sipser
