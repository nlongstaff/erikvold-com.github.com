---
title: Regular Expression to determine if a base 10 number is divisible by 3
tags: Regular Expressions, Programming
---
I decided to work out the regular expression for matching mod3=0 positive <a title="Decimal" rev="vote-for" target="_blank" href="http://en.wikipedia.org/wiki/Decimal">decimal (base 10)</a> <a title="Integer" rev="vote-for" target="_blank" href="http://en.wikipedia.org/wiki/Integer">integers</a> today. 
I had a dream about the problem last night (remembering an old lecture) and could not find my notes with the solution (if I even wrote it down). 
So, after googling around for a bit, I gave up, and worked the solution out myself, because it looks like a good void to fill on the interwebs.
</p>

<h2>The Problem:</h2>
<p>
Let <em>L</em> = { w | w mod 3 = 0 }, where the alphabet is {0,1,2,3,4,5,6,7,8,9}; give the <a title="Deterministic finite-state machine" rev="vote-for" target="_blank" href="http://en.wikipedia.org/wiki/Deterministic_finite-state_machine">Deterministic Finite Automaton</a> (<abbr title="Deterministic Finite Automaton">DFA</abbr>) for <em>L</em>, and convert this to a <a title="Regular Expression" target="_blank" rel="external" rev="vote-for" href="http://en.wikipedia.org/wiki/Regular_expression">regular expression</a>.
</p>

<p>&nbsp;</p>

<h2>The Solution (don't peak):</h2>

  	<a href="http://erikvold.com/blog/index.cfm/2008/11/10/regular-expression-to-determine-if-a-base-10-number-is-divisible-by-3#more" name="more" rel="nofollow"></a>
		<p>
The <abbr title="Deterministic Finite Automaton">DFA</abbr> ( <i>S</i>, Σ, <i>T</i>, <i>s</i>, <i>A</i> ):<br>
<i>S</i> = {q0,q1,q2}<br>
Σ = {0,1,2,3,4,5,6,7,8,9}<br>
T = (doing the state diagram below)<br>
<i>s</i> = {q0}<br>
<i>A</i> = {q0}
</p>

<p>
For shorthand I will divide the alphabet, ?, into:
</p><ul>
<li>A={0,3,6,9}</li>
<li>B={1,4,7}</li>
<li>C={2,5,8}</li>
</ul>
<p></p>

<p>
The state diagram:<br>
</p><div class="center"><img title="Step 1: DFA State Diagram" alt="DFA State Diagram" src="/blog/images/posts/2008-9-11/dfa-state-diagram.jpg"></div>
<p></p>

<p>
Now to convert the <abbr title="Deterministic Finite Automaton">DFA</abbr> state diagram into a regular expression. This is done by converting the <abbr title="Deterministic Finite Automaton">DFA</abbr> into <a title="Generalized nondeterministic finite state machine" rev="vote-for" target="_blank" href="http://en.wikipedia.org/wiki/GNFA">Generalized Non Deterministic Finite Automaton</a> (<abbr title="Generalized Non Deterministic Finite Automaton">GNFA</abbr>), and then converting the <abbr title="Generalized Non Deterministic Finite Automaton">GNFA</abbr> into a regular expression.<br>
</p><div class="center"><img title="Step 2: Conversion of DFA into GNFA, and removal of q0 state" alt="Conversion of DFA into GNFA, and removal of q0 state" src="/blog/images/posts/2008-9-11/step2.jpg"></div>
Notice in the above that I did two steps in one; I first converted the <abbr title="Deterministic Finite Automaton">DFA</abbr> into a <abbr title="Generalized Non Deterministic Finite Automaton">GNFA</abbr> (which is the easy part), then I removed the q0 state.
<p></p>

<p>
Removing the q1 state:<br>
</p><div class="center"><img title="Step 3: Removing the q1 state" alt="Removing the q1 state" src="/blog/images/posts/2008-9-11/step3.jpg"></div>
<p></p>

<p>
Finally, removing the q2 state:<br>
</p><div class="center"><img title="Step 4: Removing the q2 state" alt="Removing the q2 state" src="/blog/images/posts/2008-9-11/step4.jpg"></div>
<p></p>

<p>
Therefore the regular expression that defines the regular language <em>L</em> is:<br>
(A+)∪((B∪A*B)(A∪CA*B)*CA*)∪((C∪A*C∪(B∪A*B)(A∪CA*B)*(B∪CA*C))(A∪BA*C∪(C∪BA*B)(A∪CA*B)*(B∪CA*C))*(BA*∪(C∪BA*B)(A∪CA*B)*CA*))
</p>

<p>For further reading please see "<a title="Introduction to the Theory of Computation" rel="external nofollow" rev="vote-for" target="_blank" href="http://books.google.com/books?id=eRYFAAAACAAJ">Introduction to the Theory of Computation</a>" by Michael Sipser</p>
