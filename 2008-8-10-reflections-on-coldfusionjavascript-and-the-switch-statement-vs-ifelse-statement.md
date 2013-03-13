---
title: Reflections on Coldfusion/Javascript and the switch statement vs if...else statement
tags: Javascript, Coldfusion, Programming
---
So, I was reading a recent discussion on the difference between the switch statement and the if...else statement, on the <a title="CF-Talk on Google Groups" rel="external nofollow" target="_blank" href="http://groups.google.ca/group/CF-Talk">CF-Talk</a> Mailing List, and I thought I'd write about just how cool switch statements really are.</p>

<p>First I want to point out a couple of clear <strong>advantages</strong> of the switch statement over the well known if...else statement:
</p><ul>
<li>We have a single expression that is <strong>only evaluated once</strong>.</li>
<li>We can run multiple segments of code for a given value, which handy for clean code reuse.</li>
</ul><p></p>

<p>Now let's consider the <strong>downside</strong> of a switch statement:
</p><ul>
<li>The switch statement handles a subset of problems that the if-else statement can handle, albeit more efficiently in many cases where they overlap. I like to think of the switch statement as a logic factoring solution which is available to me for simple types of if...else statements.</li>
<li>Cannot use variables in the case statement (unless your using Javascript!)</li>
</ul><p></p>

<p>Here's an example of a Coldfusion if...else statement that can be simplified with a switch statement:
</p><div class="code">&lt;cfscript&gt;<br>
function cleanTeeth(meal){<br>
  if(meal eq "brunch"){<br>
    useToothPick();<br>
  }<br>
  else if(meal eq "breakfast"){<br>
    useMouthWash();<br>
    floss();<br>
    useToothBrush();<br>
  }<br>
  else if(meal eq "lunch"){<br>
    useToothBrush();<br>
  }<br>
  else if(meal eq "dinner"){<br>
    floss();<br>
    useToothBrush();<br>
  }<br>
}<br>
&lt;/cfscript&gt;</div><p></p>

<p>Now here is the simplified switch statement version:
</p><div class="code">&lt;cfscript&gt;<br>
function cleanTeeth(meal){<br>
  switch(meal){<br>
    case "brunch":<br>
      useToothPick();<br>
      break;<br>
    case "breakfast":<br>
      useMouthWash();<br>
    case "dinner":<br>
      floss();<br>
    case "lunch":<br>
      useToothBrush();<br>
  }<br>
}<br>
&lt;/cfscript&gt;</div><p></p>

<p>So in this example, not only is the switch statement version reusing code, making it less lines, but it should run faster, especially if you eat a lot.</p>

<p>Now, the thread I read on Cf-Talk began with someone asking why one cannot use a variable in a Coldfusion case statement, and the short answer to this was that Java won't let you do this in a switch statement either. Java will allow you to use constants in a case statement, as was pointed out in the thread, but since constants do not exist in Coldfusion, they cannot be used in a Coldfusion case statement. I suppose this functionality could be implemented into the Coldfusion switch statement, but that would mean that Coldfusion switch statements would simply be converted to Java if..else statement, and lose the performance gained by being a Java switch statement.</p>

<p>But anyhow, the point I wanted to make was that in Javascript using a variable in the case statement is possible! so when you Coldfusion/Java programmers are writing some Javascript next time, heads up.</p>
