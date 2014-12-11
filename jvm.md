# JVM tuning, debugging og profiling tipps




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
