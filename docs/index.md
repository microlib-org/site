# Welcome to Microlib.org

What is a microlib?

## Microlib definition

A python package is called a microlib, if all of the 
following are true:

* **Small**: Not more than 5 public classes or functions
* **Restricted**: The microlib should do one thing and do it well, no vague responsibilities.
* **Tested**: 100% test coverage
* **Cohesive**: 100% third-party dependency cohesion
* **Documented**: Has at least one clear use case for every public definition

Why do we want to follow these principles?

## Why keep it ...

#### Small?

Why keep it small? Because it will take very short time for a developer to get 
familiar with the microlib.

#### Restricted?

Why keep it restricted? The microlib should do one thing and do it well, for these 
reasons:

* It takes a very short time to get familiar with the goals of the microlib.
* It is easier to spot bugs, since more people can understand the goals.
* If there is a security vulnerability in the microlib, it affects only the microlib,
nothing else.
* Easier to test, since there are clear goals.

#### Tested?

This is self-explanatory. Since the microlib will be used by many users, even the 
smallest bug can cause so much suffering. For this reason, we need to make sure that
the microlib works as intended, and since the microlib's goals are clearly defined,
it should be easy to reach 100% test coverage.


#### Cohesive?

If there is a third-party dependency that is only needed in one or two of our public
definitions, we should ship this as a separate microlib. Because if a user only 
needs the other public definitions, it will bring an unneeded third-party dependency
and increase the chance of environment conflicts or security vulnerability.

#### Documented?

Since the microlib will be used by many users, we need to make the documentation as
clear as possible: concise and to the point about every public definition.

Every public definition should have at least one clearly defined use case, otherwise
it contradicts Extreme programming principles.
