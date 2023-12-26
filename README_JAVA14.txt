Compile Sample.java and run it.  The output should be like this:

Switch expressions with pattern matching: No longer need to use `--preview`

Run Fortify Static Code Analyzer to scan the code:

$ sourceanalyzer -b sample -clean
$ sourceanalyzer -b sample -source 14 Sample.java
$ sourceanalyzer -b sample -scan -f Sample.fpr

Open the results in Audit Workbench:

$ auditworkbench Sample.fpr

The analysis results should contain vulnerabilities in the following categories:

      Privacy Violation
      J2EE Bad Practices: Leftover Debug Code

The analysis results might include other issues depending on the version of the Rulepacks used in the scan.

In this sample, the Privacy Violation vulnerability indicates that sensitive data is written
to the console.

The J2EE Bad Practices vulnerability indicates the presence of a main()
method, which should not appear in a J2EE application. Because this is not
a J2EE application, this vulnerability category does not apply.
We can configure which rule categories are displayed based on
the type of application using the Audit Guide in Audit Workbench.
