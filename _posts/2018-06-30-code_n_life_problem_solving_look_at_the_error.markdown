---
layout: post
title:      "Code N' Life Problem Solving: Look at the Error"
date:       2018-07-01 03:21:25 +0000
permalink:  code_n_life_problem_solving_look_at_the_error
---


def methoda
  variable1 = "alpha"
	variabe2 = "beta" 
	puts "There is always a single #{variable1}, but there may be more than one #{variable3}."
end *

The code above will not run the way it was likely intended. There are many ways to see it is not working, but ultimately we all have to follow the same logic route. The result was not as expect. There is an issue. What is the problem and how can we fix it? Can it be fixed? 
  Let's talk about problems. The above code has a simple enough solution, but what if that code was buried deep within hundreds of lines of code? A coder might simply say, "look at the error". That thought is really quite useful in both life and coding. 
	A good friend once stated, "The biggest problem with solving a problem, is knowing the problem." He further went on to explain that most of what makes a question difficult to answer is the ignorance of the real question. After prying him for a better explanation, he said, "The more questions you can answer about a question: the more clear an answer becomes". He gave me an example. Alas, the years have stolen away that memory, so I will provide a different example:
	"A woman begins driving a vehicle. How many women are sitting on the vehicle?"
	Some might immediately answer, but most people will question the question. What type of vehicle? A bus can hold many people. A motorcycle can only hold one or two, depending on seats. Who else is on the vehicle? If it's a man on a motorcycle, we know the answer to the question: 1 woman. If Mary, Stacy, and Joanna are on a bus, we can presume the answer becomes 4 women. Point in case: the more questions about the question, the more clear the original answer becomes. 
	Back to code. Code provides error codes that often point to exactly where the error happened. That is super helpful and answers a question about the error. However, that is sometimes not enough. When I first began coding, an error was hugely frustrating. What is all this red gibberish? Why isn't my code working? WHAT IS WRONG? Over the years in life, and over the thousands of coding errors, I've begun asking another question:
	"What is RIGHT?" 
	This answers another question about the problem. If other lines are functioning properly, we begin to get a sense of direction. I equate this to using a foreign shower. Say we visit our friends house and go for a swim. After, we all decide to take showers. We take showers all the time, simple! We go to turn on the water. OUCH! It's scalding hot! There is a problem. Error code line 23: the handle was rotated to a position that is not suitable for bathing. We know where the problem is. Which direction do we move the knob to get the temperature comfortable? We look at the knob and see that the markings are faded. Well, that doesn't help. Next, we rotate the knob full tilt to a direction, and the water stops running entirely. Not what we were trying to do, but it answers: What is working RIGHT?
	Now, we know the direction for on and off works properly. From this, we can start the water again, testing the temperature in increments away from 'off'. Eventually, we see that the temperature was coldest when we first turned the water on, so we are able to adjust somewhere in the middle for a comfy shower.
	The way we solve problems boils down to knowing more about them. What makes the problem better? Worse? Unchanged? Coding follows a similar pattern.

def method_a
  variable_1 = "alpha"
	variabe_2 = "beta" 
	puts "There is always a single #{variable_1}, but there may be more than one #{variable_3}."
end 

  Our error will likely flag "rb: 4", leading us to the puts statement. It may even outright tell us, "undefined local variable or method 'variable_3' for main:Object". Ok, any coder is likely going to figure out the problem very quickly with that information. How? We look at our variables and see that there is a variable_2, but not a variable_3.  We presume the code within puts should have listed variable_2, and the problem is fixed. We run the test again, and there is still an error.
	At this point, the rushed coder slows down. How can the code still be broken, in the exact same place with the same error: undefined local variable.
	We slowly comb over the variables. We see a difference, one says "variable" and the other "variabe". What is right? We know it should say "variable" like the first one does. 'What is right?' has been answered, allowing us to change the variable name to actually say "variable". We made a choice to change the spelling as opposed to change the call within puts. English spelling doesn't matter here though. Why did we do that then? Technically, it's faster to type the typo. We decide to choose the correct, despite longer, spelling because we know others may end up coming to work on this code later and correct spelling is a pretty good standard to follow. The choice is overly simple and quick. However, this same process of decision making is used throughout both code and life.
	We don't always follow a logical path to a solution in either code or life. However, if we strive to ask things like, "What exactly is the problem? Where? Why? What is not part of the problem?" and similar questions...I think we will have a much easier time dealing with our errors in the future.  
	
	
