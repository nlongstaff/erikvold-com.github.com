---
title: Reflections on Coldfusion/Javascript and the switch statement vs if...else statement
tags: Javascript, Coldfusion, Programming
---
So, I was reading a recent discussion on the difference between the switch statement and the if...else statement, on the [CF-Talk] (http://groups.google.ca/group/CF-Talk") Mailing List, and I thought I'd write about just how cool switch statements really are.

First I want to point out a couple of clear **advantages** of the switch statement over the well known if...else statement:

- We have a single expression that is **only evaluated once.**
- We can run multiple segments of code for a given value, which handy for clean code reuse.

Now let's consider the **downside** of a switch statement:

- The switch statement handles a subset of problems that the if-else statement can handle, albeit more efficiently in many cases where they overlap. I like to think of the switch statement as a logic factoring solution which is available to me for simple types of if...else statements.
- Cannot use variables in the case statement (unless your using Javascript!)

Here's an example of a Coldfusion if...else statement that can be simplified with a switch statement:

<div class="code">&lt;cfscript&gt;   
function cleanTeeth(meal){   
  if(meal eq "brunch"){   
    useToothPick();   
  }   
  else if(meal eq "breakfast"){   
    useMouthWash();   
    floss();   
    useToothBrush();   
  }   
  else if(meal eq "lunch"){   
    useToothBrush();   
  }   
  else if(meal eq "dinner"){   
    floss();   
    useToothBrush();   
  }   
}   
&lt;/cfscript&gt;</div><p>     

Now here is the simplified switch statement version:

<div class="code">&lt;cfscript&gt;   
function cleanTeeth(meal){   
  switch(meal){   
    case "brunch":   
      useToothPick();   
      break;   
    case "breakfast":   
      useMouthWash();   
    case "dinner":   
      floss();   
    case "lunch":   
      useToothBrush();   
  }   
}   
&lt;/cfscript&gt;</div><p>

So in this example, not only is the switch statement version reusing code, making it less lines, but it should run faster, especially if you eat a lot.

Now, the thread I read on Cf-Talk began with someone asking why one cannot use a variable in a Coldfusion case statement, and the short answer to this was that Java won't let you do this in a switch statement either. Java will allow you to use constants in a case statement, as was pointed out in the thread, but since constants do not exist in Coldfusion, they cannot be used in a Coldfusion case statement. I suppose this functionality could be implemented into the Coldfusion switch statement, but that would mean that Coldfusion switch statements would simply be converted to Java if..else statement, and lose the performance gained by being a Java switch statement.

But anyhow, the point I wanted to make was that in Javascript using a variable in the case statement is possible! so when you Coldfusion/Java programmers are writing some Javascript next time, heads up.
