# Lab 2: Second Activity: Translating Python code to Java code

The second lab activity this week will have your team practice using GitHub Issues
to divide up coding tasks and PRs to contribute code. The code itself should feel quite familiar,
as we will be translating Python code that implements some common data structures to implement the
multiset ADT.

The goals of this activity are to:
- give you practice applying a branch and merge workflow
- using pull requests to provide a mechanism to ensure other team members can review code contributed
  to a software project before it is accepted into the main branch
- give you a first experience of coding in a collaborative environment
- experiment with how to most effectively divide up coding tasks

# The Task

Now that we are familiar with the process of branching and making pull requests from the
previous activity, we will apply these new skills to a coding task.

>Note: this may seem like a big task at first, but it won't be so daunting as your team splits
> up the coding tasks!

In this task, your goal is to translate the Python code from `python/multiset.py` into a
functionally equivalent set of Java classes. There will be a lot of things that directly
translate and others where you'll have to muddle through some unfamiliar syntax. **We don't
expect you will get it fully working during lab, but the goal is to make some progress and
get a sense of what it will be like to work in a team throughout the term. Try things out
today, and don't be afraid to make mistakes!**

## Setting expectations
- Aim to create at least two GitHub Issues per team member.
  - Aim to close at least one GitHub Issue per team member.
- Aim to make at least one pull request per team member.
- Aim to have each team member review at least one pull request.
- Actively discuss with your team and those around you to develop strategies for effectively
  working on a shared code base.
- Have code in your repo on GitHub that passes all the provided tests
  (these are for a subset of the overall coding task).

## The code

You will be developing code for several classes that implement a MultiSet ADT and
completing a main method equivalent to the provided Python main block.

The main block of the provided Python code runs a timing experiment to compare the various implementations.
It should feel quite similar to code you would have seen in a first-year CS course.

## Submission

> Reminder that the lab this week is NOT submitted for credit, but your team should still go
> through the process of submitting on MarkUs to get used to the process.

Your team will submit a link to your GitHub repo on MarkUs in the "week2git assignment",
as you did in lab 1. The provided tests from this repo are included as self tests on MarkUs,
as well as some additional tests to check that your team created Issues and made PRs as outlined
in the instructions below.

## Instructions

Choose one member of your team to make a fork of
https://github.com/CSC207-2025F-UofT/lab2-multiset-adt.

- [X] The repository owner can then add the other members as collaborators of this repository
  so that everyone has access to it. This is so that your team has a shared remote repo to which
  your group can all contribute.

---

- [X] Get a local copy of this remote repo.
  You can do this by either method from last week: git clone <url>
  or creating a new project from version control in IntelliJ.

---

- [X] Take the time to skim the rest of the instructions to get a better sense of what you'll be doing
  in this activity. If you have any immediate questions, raise these with your group or ask your TA.

---

- [X] As a team, explore the Python code base and identify specific pieces of code that will need to
  be completed. You can also look at what parts we have already provided in the starter code.
  (See the general strategies and advice further below, ask other groups, or ask your TA for advice as needed.)
    - The later "Initial Advice" section highlights a few aspects of the code that your team should think
    - about as you explore the code.

---

- [X] Based on your group discussion, your team should create GitHub Issues listing the tasks your team
  needs to complete.

---

- [X] Once your team has this set of Issues, each member should be assigned an Issue to start working on.

---

- [ ] On a branch, locally develop the code such that your assigned Issue is completed.

---

- [ ] Push your **branch** to the remote repository and create a PR.

---

- [ ] When someone on your team has made a PR, a subset of your team should take the time
  to review it. You can pull their branch from the remote repository and try running the code locally
  and also review the code on GitHub. Practice giving both verbal feedback (in person) and written feedback
  (on GitHub) during the lab today.

---

- [ ] Once everyone has made a successful PR and had it merged in, your team should continue
  working to close more of the Issues that you opened. This will help you practice the branch and merge workflow.

---

- [ ] Towards the end of the lab, your team should take some time to reflect on what worked well
  and where you encountered difficulty as you worked on the code and divided up tasks between members of your group.

---

### Initial Advice
A few general strategies before we begin:

1. The goal is to get the whole program to function, but you'll want to get bits and pieces up and
   running, incrementally. Ideally, you can identify independent pieces which can be developed in isolation
   and won't cause any conflict when merged in later. For example, since we have defined an abstract class
   representing what it means to be a `MultiSet`, you can work on both sides of that public interface:
   * (1) develop client code which makes use of the public interface and
   * (2) write any classes which then implement that public interface.
2. Each class should go in its own file in Java, so splitting up work by class is one way to help
   avoid conflicts.
3. Within a class, there may be several methods to be written, so you can also divide up work that way.
4. Ideally, we would have some way to be confident that our code will work once implemented, so writing
   some more tests might be worth considering. Of course, we haven't talked about writing tests in Java yet, so
   it is okay if your team decides not to write any additional tests in lab today, but you can use the
   provided ones as examples to develop your own tests based on!
5. Lastly, remember that we will want whatever code is in the `main` branch to always be error free,
   so try to plan the order of work and pull requests being merged in to ensure
   errors never make it into the `main` branch.

**And, to reiterate, you shouldn't expect to complete the code in lab, but rather experience the process
of attempting to tackle a relatively large coding task in a collaborative, team setting.**

### Java Concepts

While not exhaustive, the below are a few concepts that you may be seeing for the first time today or only
just recently in your Java learning. You'll learn more about them over the next couple of weeks in the course,
so don't worry if you find it challenging to implement parts of the code. You should find that there are still
parts of the code you are able to write given your current knowledge of Java.

Importantly, you should be getting in the habit of looking up new concepts and actively searching
for information as you need it. The official Java documentation, the course notes, and the official Java
tutorials are all resources that you shouldn't hesitate to refer to as needed. And, of course, your TA and
peers will also be invaluable sources of information.

Below just very briefly highlights some key concepts you'll need to explore as you implement the code
today. Again, we don't expect you to know all of these things coming in, so the exercise is largely
getting you to identify what you can implement and what you will need to look up or ask questions about
in order to make progress on the code.

#### Abstract Classes

In the Python code, we had represented an ADT as an abstract class (`MultiSet`). To represent an ADT in Java,
we can also create an abstract class. An interface specifies an API (set of public methods) which
other classes can then implement. Importantly, a non-abstract subclass of an abstract class needs to
implement **all** abstract methods defined in its parent class.

Note: you may have heard about `interfaces` in Java; since the `MultiSet` consists entirely of abstract methods
and no attributes, it can naturally be defined as an `interface` instead of an abstract class. We'll talk much more
about `interfaces` throughout the course (and you'll see them in your prep readings for Module 1)!

#### Constructors

These are like the special `__init__` methods in Python when we want to initialize (or construct) an
instance of a class. To actually create a new instance of a class, you'll need to use the `new` keyword
and call a constructor for the class.

#### Delegation / Composition

The provided code for classes like `BST` and `BSTMultiSet` demonstrates a common design pattern where
one class wraps another by storing it as a private instance variable. Rather than implementing all
functionality directly, the wrapper class **delegates** work to the internal object. This approach is
useful for organizing code, controlling access, or adapting interfaces. Once you're familiar with the
public methods of the wrapped class, writing a wrapper is usually straightforward!

#### Access Modifiers

In the Python code, you'll note the use of a leading underscore to mark an attribute as being private
(an implementation detail) of a class. Java uses access modifiers to specify who can access things like
classes, methods, and variables. A couple general rules: (1) the methods specifying your API need to be
public and (2) default to making all instance variables private unless you have a reason not to.

#### JavaDoc

We haven't talked about documentation too much, but you can look at how existing Java code is
documented to get a sense of the standards used. For example, if you hover over any class name
in IntelliJ, what you see is the JavaDoc for that class (same idea as docstrings in Python).

#### Generics

Thinking back to your code for common ADTs in first year,
you may recall the use of the `Any` type annotation to indicate that the ADT could contain "any" kind
of object. For this exercise, we have written a simplified version of the code which assumes we are
only storing integers.

In Java, we'll soon learn about the concept of Generics to specify what type of objects a given
instance of our ADT will store. Once we learn about Generics, we encourage you to look back at this code
and generalize it to make use of Generics.

#### The Java Collections Framework (JCF)
The JCF is the realization of ADTs in Java. We'll learn more about it this framework soon, and you will
make use of it throughout the term anytime you want to store collections of objects or perform common
tasks related to collections of objects.

Code similar to what you implement here is present in the JCF, but with additional Java features,
like Generics and Interfaces which we'll learn more about.

## Extra

If your team does fully replicate the behaviour of the provided Python code, we encourage
you to think about possible changes or extensions you could make to the code:

- could we make the timing experiment code more customizable and able to time other things?
  - for example, how might we allow a user to vary the problem sizes for an experiment
  or customize what statistics are reported?

- how can you use Generics to generalize the `MultiSet` ADT to contain any kind of objects?

- how does the code change if we make the `MultiSet` ADT a Java Interface instead of an abstract class?
