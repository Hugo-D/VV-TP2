# Using PMD

Pick a Java project from Github (see the [instructions](../sujet.md) for suggestions). Run PMD on it source code using any ruleset. Describe below an issue found by PMD that you think should be solved (true positive) and include below the changes you would add to the source code. Describe below an issue found by PMD that is not worth solving (false negative). Explain why you would not solve this issue.

## Answer

Command launched to execute PMD over the [Apache Common Maths](https://github.com/apache/commons-math) source code using the QuickStart rueleset for Java:

```sh
sudo ./pmd-bin-6.32.0/bin/run.sh pmd -d ~/Bureau/commons-math-master.zip -f text -R rulesets/java/quickstart.xml
```

Issue found by PMD that we think should be solved: `SingleMethodSingleton:  Class contains multiple getInstance methods. Please review.` at [complex/ComplexFormat.java:39](https://github.com/apache/commons-math/blob/0300f97d74fa0207570b5ea3ecadbf9896d3ecc4/src/main/java/org/apache/commons/math4/complex/ComplexFormat.java#L272)

Changes we would add to the source code:
 
```Java
public abstract StringBuffer format(Object obj, StringBuffer toAppendTo,
                               FieldPosition pos);
```

We define the function `format` as an abstract function, then forcing the children classes to implement `format` by themselves according to their own class without the need of a call to `instanceof` (here the children classes are `Complex` and `Number`).

Issue found by PMD that in our opinion is not worth solving: `UselessParentheses:     Useless parentheses.` at [analysis/differentiation/DSCompiler.java:350](https://github.com/apache/commons-math/blob/0300f97d74fa0207570b5ea3ecadbf9896d3ecc4/src/main/java/org/apache/commons/math4/analysis/differentiation/DSCompiler.java#L350)

This issue doesn't impact the well-behaving of the code, moreover it enhances its readability. 
