# TCC *vs* LCC

Explain under which circumstances *Tight Class Cohesion* (TCC) and *Loose Class Cohesion* (LCC) metrics produce the same value for a given Java class. Build an example of such as class and include the code below or find one example in an open-source project from Github and include the link to the class below. Could LCC be lower than TCC for any given class? Explain.

## Answer

*Tight Class Cohesion* and *Loose Class Cohesion* metrics produce the same value for a given Java class when there isn't any indirect connections between the methods of the class.

<ins>Example:</ins> [Apache Common CLI - OptionGroup.java](https://github.com/apache/commons-cli/blob/master/src/main/java/org/apache/commons/cli/OptionGroup.java)

**3** variables and **8** methods:
![TCC and LCC graphs for the Apache Common CLI - OptionGroup.java](https://drive.google.com/file/d/1e6Rhqvj9sr8EAH3me_C-kfWZGB16L8bt/view?usp=sharing)

NP: maximum number of possible connections = 8*(8-1)/2 = 28
TCC = 5/28
LCC: no indirect connections = 5/28

5/28 < 0.5 we can consider the class OptionGroup to be non-cohesive.

TCC is the number of direct connections over the number of possible connections while LCC is the sum of direct and indirect connections over the number of possible connections. Thus, LCC is always equal or higher than TCC.
