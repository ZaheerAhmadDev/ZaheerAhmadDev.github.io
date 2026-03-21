1   <?xml version="1.0"?>
2   <!DOCTYPE module PUBLIC
3             "-//Checkstyle//DTD Checkstyle Configuration 1.3//EN"
4             "https://checkstyle.org/dtds/configuration_1_3.dtd">
5   
6   <module name = "Checker">
7       <property name="charset" value="UTF-8"/>
8   
9       <!-- do not change severity to 'error', as that will hide errors caused by exceptions -->
10      <property name="severity" value="warning"/>
11  
12      <!-- haltOnException is required for exception fixes and reporting of all exceptions -->
13      <property name="haltOnException" value="false"/>
14  
15      <!-- BeforeExecutionFileFilters is required for sources of java9 -->
16      <module name="BeforeExecutionExclusionFileFilter">
17          <property name="fileNamePattern" value="module\-info\.java$" />
18      </module>
19  
20      <module name="TreeWalker">
21  
22      <module name="MissingJavadocType">
23        <property name="scope" value="private"/>
24      </module>
25  
26           <!-- as we run on regression even on non-compiled files we need to skip exceptions on them -->
27           <property name="skipFileOnJavaParseException" value="true"/>
28           <property name="javaParseExceptionSeverity" value="ignore"/>
29  
30           <!-- Example of checkstyle Check usage -->
31           <!-- PLEASE CHANGE IT TO CHECK YOU ARE TESTING !!!! -->
32           <module name="ThrowsCount">
33               <property name="max" value="20000000"/>
34           </module>
35  
36           <!-- Example of sevntu.checkstyle Check usage -->
37           <!-- <module name="NestedSwitchCheck"/> -->
38  
39           <!-- suppress javadoc parsing errors, as we test Check not a parser -->
40           <module name="SuppressionXpathSingleFilter">
41              <property name="message" value="Javadoc comment at column \d+ has parse error"/>
42           </module>
43      </module>
44      <!-- Example of filter -->
45      <!--
46      <module name="SeverityMatchFilter">
47          <property name="severity" value="warning"/>
48          <property name="acceptOnMatch" value="false"/>
49      </module>
50      -->
51  
52  </module>
