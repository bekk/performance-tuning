# JVM tuning, debugging og profiling tipps

jps - JVM process status tool

jstack - thread dump
jmap - memory map
jhat - Java Heap Analysis Tool

jstat - Java Virtual Machine statistics monitoring tool
jcmd
jinfo


jmc - Java Mission Control
jconsole
jvisualvm


## Thread dump

# Memory dump

##  Se live hvordan klassehistogrammet set ut. 

    jmap -histo:live 23158 | head -n 40

# JVM tuning

## System properties
-Dcom.sun.xml.messaging.saaj.soap.saxParserPoolSize=75
-Djavax.xml.parsers.DocumentBuilderFactory=com.sun.org.apache.xerces.internal.jaxp.DocumentBuilderFactoryImpl
-Djavax.xml.transform.TransformerFactory=com.sun.org.apache.xalan.internal.xsltc.trax.TransformerFactoryImpl
-Dcom.sun.org.apache.xalan.internal.xsltc.dom.XSLTCDTMManager=com.sun.org.apache.xalan.internal.xsltc.dom.XSLTCDTMManager
