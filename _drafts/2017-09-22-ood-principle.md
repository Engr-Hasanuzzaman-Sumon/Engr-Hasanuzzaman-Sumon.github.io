---
layout: post
title:  API testing using Postman
categories: OOD
subcategory: Intermediate
---

Single Responsibility: 
-- check where class is highly cohesive to SRP or not
---- ask all of the methods using 'Please Mr. Class, what is your function_name?
----- try to describe your class simply if it does not need and or or then it is highly                  cohesive to SRP

# how to code will be easy to change in future?
1. Depend on Behavior, Not Data
--- Behavior is captured in methods
--- every tiny bit of behavior lives in one and only
one place (DRY)
--- keep data within wrapper behavior (method) that will be to adjust in furure
** do not use instance variable even with in same class instead use private wrapper method 

2. Hide Data Structures
-- Hide complex data structure in 'Struct' so that only it know the meaning of data

3. Enforce Single Responsibility Everywhere
-- Extract Extra Responsibilities from Methods 
---- ask them questions about what they do and try to
describe their responsibilities in a single sentence

Methods that have a single responsibility confer the follow-
ing benefits:
• Expose previously hidden qualities
• Avoid the need for comments
• Encourage reuse
• Are easy to move to another class

N.B: If a bit of code inside a method needs a comment, extract that bit into a separate method. The new method name serves the same purpose as did the old comment.

4. Isolate Extra Responsibilities in Classes
-- if you found something that should not be in here and you are not convinced to create new class for that then use ruby 'Structure' to keep that unwanted behavior. 
-- If you have a muddled class with too many responsibilities, separate those
responsibilities into different classes
-- If you identify extra responsibilities that you cannot yet remove, isolate them (like using Structure)

Managing Dependencies 
1. Understanding Dependencies

2. Recognizing Dependencies
• The name of another class. Gear expects a class named Wheel to exist.
• The name of a message that it intends to send to someone other than self .
Gear expects a Wheel instance to respond to diameter .
• The arguments that a message requires. Gear knows that Wheel.new requires a
rim and a tire .
• The order of those arguments. Gear knows the first argument to Wheel.new
should be rim , the second, tire .
-- a class should know just enough to do its job and not one thing more

3. Coupling Between Objects (CBO)
-- The more Gear knows about Wheel , the more tightly coupled they are. The more tightly coupled two objects are, the more they behave like a single entity.
N.B: A day will come when it’s easier to rewrite everything than to change anything.
- 4 Other Dependencies





