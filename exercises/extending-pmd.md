# Extending PMD

Use XPath to define a new rule for PMD to prevent complex code. The rule should detect the use of three or more nested `if` statements in Java programs so it can detect patterns like the following:

```Java
if (...) {
    ...
    if (...) {
        ...
        if (...) {
            ....
        }
    }

}
```
Notice that the nested `if`s may not be direct children of the outer `if`s. They may be written, for example, inside a `for` loop or any other statement.
Write below the XML definition of your rule.

You can find more information on extending PMD in the following link: https://pmd.github.io/latest/pmd_userdocs_extending_writing_rules_intro.html

Use your rule with different projects and describe you findings below. See the [instructions](../sujet.md) for suggestions on the projects to use.

## Answer

The XPath rule:
```java
<rule name="ifs3imbrication_vv-tp2"
      language="java"
      message="No code with 3 or more ifs intricated in 1 another is allowed"
      class="net.sourceforge.pmd.lang.rule.XPathRule">
   <description>
Answer to VV-T2 - Extending PMD
   </description>
   <priority>5</priority>
   <properties>
      <property name="version" value="2.0"/>
      <property name="xpath">
         <value>
<![CDATA[
//IfStatement/Statement/Block/BlockStatement/Statement
//IfStatement/Statement/Block/BlockStatement/Statement
//IfStatement
]]>
         </value>
      </property>
   </properties>
</rule>
```
