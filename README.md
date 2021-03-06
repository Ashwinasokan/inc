# Taint Analysis of Java Programs using incremental Slicing

A project to develop a incremental data flow analyzer for Java bytecode programs on top of [WALA](http://wala.sourceforge.net).

[Presentation Slides](https://github.com/Ashwinasokan/Inc/blob/master/presentation.pdf)

[Project Report](https://github.com/Ashwinasokan/Inc/blob/master/report.pdf)

There are two basic blocks,

1. Slice Analysis
Input [initial program's call graph, Seed variables]
Output [slice for given seed variable, data flow facts against each program point]

2. Incremental Analysis
Input [initial program's call graph, seed variables, slice for given seed variables, data flow facts from previous iteration]
Output [Revised Slice, Revised data flow facts from previous iteration]

To run:

Under project root folder, sbt "run version1ClassPath version2ClassPath seedVariableNumber"

Seed variable number is SSA variable number generated by WALA IR form. This need to be fixed & abstracted, but for the time being it need to be passed explicitly as such.

example, sbt "run tests/SliceV1.class tests/SliceV2.class 4"

sbt "run tests/FactorialV1.class tests/FactorialV2.class 4"

Examples Folder: tests

1. Constant.java

2. Factorial.java

3. Slice.java

4. Search.java

5. Sort.java
