---
title: Regular Expression to Determine if a Base 10 Number is Divisible by 5
tags: Regular Expressions
---
This regular expression is a really easy one to write, but it will highlight that when writing regular expressions, it is sometimes easier to skip writing the <a title="Deterministic Finite Automaton" target="_blank" href="http://en.wikipedia.org/wiki/Deterministic_finite-state_machine">DFA</a>; which provided to be a useful step when I created a <a title="Regular Expression to determine if a base 10 number is divisible by 3" target="_blank" href="http://erikvold.com/blog/index.cfm/2008/11/10/regular-expression-to-determine-if-a-base-10-number-is-divisible-by-3">regular expression to determine if a base 10 number is divisible by 3</a>.

<h2>The Problem:</h2>
<p>
Let <em>L</em> = { w | w mod 5 = 0 }, where the alphabet is {0,1,2,3,4,5,6,7,8,9}; give the DFA for <em>L</em>, and convert this in to a regular expression.
</p>

<p>&nbsp;</p>

<h2>The Solution:</h2>

  	<a href="http://erikvold.com/blog/index.cfm/2008/11/28/regular-expression-to-determine-if-a-base-10-number-is-divisible-by-5#more" name="more" rel="nofollow"></a>
		<p>
The DFA ( <i>S</i>, Σ, <i>T</i>, <i>s</i>, <i>A</i> ):<br>
<i>S</i> = {q0,q1}<br>
Σ = {0,1,2,3,4,5,6,7,8,9}<br>
T = (doing the state diagram below)<br>
<i>s</i> = {q0}<br>
<i>A</i> = {q0}
</p>

<p>
For shorthand I will divide the alphbet, Σ, into:
</p><ul>
<li>A={0,5}</li>
<li>B={1,2,3,4,6,7,8,9}</li>
</ul>
<p></p>

<p>
The state diagram:<br>
</p><div class="center"><img title="Step 1: DFA State Diagram" alt="DFA State Diagram" src="/blog/images/posts/2008-11-28/5mod0-base10-dfa-part1.jpg"></div>
<p></p>


<p>
Now to convert the DFA state diagram into a regular expression. This is done by converting the DFA into <a title="Generalized nondeterministic finite state machine" rev="vote-for" target="_blank" href="http://en.wikipedia.org/wiki/GNFA">GNFA</a>, and then converting the GNFA into a Regular Expression.<br>

</p><div class="center"><img title="Step 2: Conversion of DFA into GNFA, and removal of q0 state" alt="Conversion of DFA into GNFA, and removal of q0 state" src="/blog/images/posts/2008-11-28/5mod0-base10dfa-part-2.jpg"></div>
Notice in the above that I did two steps in one; I first converted the DFA into a GNFA (which is the easy part), then I removed the q0 state.
<p></p>


<p>
Finally, removing the q1 state:<br>
</p><div class="center"><img title="Step 3: Removing the q1 state" alt="Removing the q1 state" src="/blog/images/posts/2008-11-28/5mod0-base10-dfa-part3.jpg"></div>
<p></p>

<p>
Therefore the Regular Expression that defines the Regular Language <em>L</em> is:<br>
A∪B(B∪A+B)*A+
</p>

<p>For further reading please see "<a title="Introduction to the Theory of Computation" rev="vote-for" target="_blank" href="http://books.google.com/books?id=eRYFAAAACAAJ">Introduction to the Theory of Computation</a>" by Michael Sipser</p>
