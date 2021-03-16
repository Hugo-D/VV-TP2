# TCC *vs* LCC

Explain under which circumstances *Tight Class Cohesion* (TCC) and *Loose Class Cohesion* (LCC) metrics produce the same value for a given Java class. Build an example of such as class and include the code below or find one example in an open-source project from Github and include the link to the class below. Could LCC be lower than TCC for any given class? Explain.

## Answer

*Tight Class Cohesion* and *Loose Class Cohesion* metrics produce the same value for a given Java class when there isn't any indirect connections between the methods of the class.

<sub>Example:</sub> [Apache Common CLI - OptionBuilder.java](https://github.com/apache/commons-cli/blob/master/src/main/java/org/apache/commons/cli/OptionBuilder.java)

**7** variables and **12** methods:
![TCC and LCC graphs for the Apache Common CLI - OptionBuilder.java](https://docs.google.com/drawings/d/1Ar0M9Ol-eqPJXO3um66PnCMUn5n-yNkjm0fn38BhXyA/edit?usp=sharing)

TCC is the number of direct connections over the number of possible connections while LCC is the sum of direct and indirect connections over the number of possible connections. Thus, LCC is always equal or higher than TCC.
