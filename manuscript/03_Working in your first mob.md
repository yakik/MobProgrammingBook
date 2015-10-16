# Working in Your First Mob

## Heuristic

If everything is going right, rotation will not disrupt the direction which the mob is going.

## Preparing the navigator

Part of having a good mobbing experience is being able to have a clear direction that is shared throughout the team. A few little tricks can be done to enable this to happen as it is not a habit most people have acquired yet.

Ask the navigator what they are going to do. Here's some examples of when a navigator has a clear direction versus when they are lost.

Lost:

**Q**: What are you going to do?  
**A**: I don't know.   
**A**: Something with the test.   
**A**: Get it to work.   
**A**: The next scenario.   
**A**: (stares blankly)

Has direction:

**Q**: What are you going to do?  
**A**: The code does not compile. We need to fix that.  
**A**: We need to write the test for handling positive numbers.  
**A**: I'd like to give that paragraph a better name.  
**A**: We haven't checked in in a while.  

Sometimes you can get to a direction through a series of questions. For example:

**Q**: What are you going to do next?  
**A**: I don't know.   
**Q**: Does the code work?  
**A**: No.  
**Q**: Why?  
**A**: It doesn't compile.   
**Q**: Why not?  
**A**: The class does not exist.   
**Q**: What are you going to do next?  
**A**: We need to create the class.

### Examples

If you are working on a task or doing test-first development, it is very useful to have an example written on a whiteboard. The examples should be very simple, and only show one path at a time. This means of conditional words like "or" or "if". If there is an example, it might take many turns before its finished, and having it on the board will give guidance for the whole team on what they need to do.

Examples should make you feel like the person telling the example actually did the thing yesterday. Imagine a teenager talking to her parent.   
"What did you do last night?"   
"I went to a friends house and played Scrabble."   
"How did the game go?"   
"Well, if I had played words on a triple letter score, then they would score three times."   
"Oh, who won?"   
"The person with the highest score."

Does this sound like the teenager actually played Scrabble last night? This is what bad examples look like. You want a concrete example.   
"How did the game go?"   
"There was three players: me, Jennifer and Samantha. Samantha went first playing the word again for 7 points. ... Jennifer ended up winning with 297 points."

Now you have an example that you can turn into code.  

These examples should be drawn on a whiteboard and they will help everybody in the team be on the same page. The really important part here is that everyone is on the same page, working from the same example.

## Consume first

It is extremely beneficial to use the consume first style of programming as opposed to more common build up style of programming. This allows the group to have a clear idea on where we are going and what is needed. Let's look at two examples to show how this works.

### Build up example

    public int x;
    public int y;
**Q**: What do you need to next?  
**A**: It's almost impossible to know what to do next right now!

The navigator had a plan, but unless you are in their head, you can't continue it on. And it is hard to check that what they were doing is correct.

### Consume first example

    Point p = new Point(10, 20);
**Q**: What do you need to next?  
**A**: Notice that Point does not compile yet. Let's create that.

    public Point(int x, int y)
**Q**: What do you need to next?  
**A**: Notice we are not holding on to the x and y.

    this.x = x;
    this.y = y;
**Q**: What do you need to next?  
**A**: Notice it does not compile. There is no this.x.

    public int x;
**Q**: What do you need to next?
**A**: There's no this.y.

    public int y;

Because the overall picture was created and used, we were able to fill in the spaces even if the navigator changes. Also, if in the very beginning it turns out that we should have used 20.5 we would have caught it right away and changed it to a double instead of an int. These kind of mistakes and assumptions happen all the time in programming. Consume first style allows the group to catch them and come to a shared understanding.

## Yes, and...

When working as a mob, it is important to follow the Yes, and... -rule of improvisational theater. The idea here is not to delete and undo what the previous navigators did before you. You can refactor but do not rewrite. This allows progress to be made continually and prevents people from being shut down in the group.

The idea is that each step in the rotation we are further ahead than we were before.

## Intentional code

Related to consume first style of programming and writing on the whiteboard, it can be very helpful to write a comment in English to state what you intend to do. Note that you can refactor this comment as well.

    //take the individual points of 6,7 and 0,0 and combine them to form a line

While this says what we want to do in English, it's not as clear as it could be. We can refactor at this point.

    //create a line from 6,7 to 0,0

Now that the English is cleaner, there's a much better chance that the result in code will be cleaner. Once the code is written, you can delete the English. It is merely a stepping stone to write from intention.

When you are translating the intention to code, you should usually end up with one line of English per one line of code. This will influence encapsulation either by methods or by classes.

### Native language

If your native language isn't English, start stating the intention in your native language. Translate to English and translate to code. Even though most groups code in English, regardless of their native language, the intention and subtleties that occur in the native language are powerful and valuable. Skipping the step of forming your intention in your native language will give you worse results.

### Code in English

A lot of time to programmers are so used to thinking in code, that you have to remind them to think in English. Here is an example I've seen a lot.

We are trying to write the method that calculates the perimeter of the triangle.   
**Q**: How do you calculate the perimeter of the triangle?  
**A**: First we create a variable to hold the perimeter.   
Next we iterate through the different sides and for each side we add the length to the existing perimeter.   
Finally we return the perimeter.

Notice two things. First, there is an awful lot of programming words in this English (variable, iterate, return). Second, the programmer is giving the comments for a for-loop implementation that is already in their head. This is not how a regular person would tell someone to calculate a perimeter.

Usually I will say something like   
**Q**:"How would you tell a child?"  
**A**:"You sum up the lengths of the sides."

Because this intention is more intentional and less prescriptive, there is a lot more freedom to come up with different code translations.

## Small steps

There are two measures to pay attention to when it comes to small steps.

1. How long has it been since you've seen feedback?
2. How long has it been since you checked in?

These two measures serve separate purposes.

The first measure of feedback lets you know if the group is taking too large steps when completing their tasks. Feedback can come in many forms. But the two big ones are from the compiler and from executing the program.

Do not worry about the feedback always being positive. Many times seeing how it fails helps us to know what success looks like. Likewise, a different type of failure is also good feedback. It lets us know that we are making progress. Finally, even seeing failure that confirms that we are where we think we are is helpful, especially for the times when we aren't.

The second measure of feedback of committed code has to do with how large of a task you are taking at a time, as opposed to making progress within a task. It is possible to very many small steps in too large of a task. Not being able to check in frequently has other negative side effects as well. If you cannot check in frequently, it can be hard to quit when you need to (lunch, end of workday, etc.). Large changes between commits can also make it hard to work with other teams because of merge conflict. If you are checking in frequently, you will not experience merge conflicts - however, other teams might. One saying that emphasizes this is:

<center><i>**Be the bird, not the statue.** </i></center>

## The Rules

It is useful to post the following rules on the wall as well as get a general working agreement from the mob.

<center><i>**We will treat everyone with kindness, consideration and respect.** </i></center>

One interesting aspect of treating each other with kindness, consideration and respect is that it tends to make everyone in the mob treat each other better and like each other more. Ironically, cognitive science teaches us that the people we treat kindly we end up liking.

Kindness is rather self-explanatory, but consideration and respect are worth going into.

### Consideration

Consideration is really about listening. This is something we don't get a lot of practice with focus on individual contribution. The place it is going to show up the most is at the driver seat. Often the driver will start by not listening to the navigator.

I usually respond to this with the usual announcements of "No thinking at the keyboard" or "There's too much thinking going on at the keyboard".

Another way that this will manifest itself is that good ideas will be spoken by members of the mob and utterly ignored. Usually these ideas are softly spoken by more introverted members. As a facilitator, it is your job to call attention to those ideas and make sure that everyone gets heard.

Over time the mob will learn the habits to listening to everyone and people will find their spots to contribute.

One final violation of consideration is when members who are not in either the designated driver or navigator spot, tune out, usually opening their laptops or phones. This can be a tricky one to handle. I prefer to handle it with environmental settings. Chairs without tables to put a laptop on, and frequent rotations will do more to keep everybody engaged than disciplining them when they are not paying attention.

### Respect

<center><i>**We always assume that the person who wrote the code before us did the best they could with the knowledge and circumstances they were in at the time they wrote it.** </i></center>  

Nothing is more corrosive than disrespect in a mob. A group can bond over making fun of some code that was written by someone else but you will pay a high price for that bonding when everybody is nervous that some day it might be them that everybody is ridiculing. We want to create a space that is safe. Safe to experiment. Safe to learn. Safe to show your vulnerabilities and weaknesses. And safe to look at and improve code without judging and criticizing the author.