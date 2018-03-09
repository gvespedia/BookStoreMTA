# Applicazione MTA Bookstore
Applicazione creata utilizzando il link di riferimento sottostante.
Riferimenti per sviluppare completamente senza accesso a WebIDE:
- Nel manifest e nei file js, le librerie node per xs vanno sostituite con [quelle di XSAdvanced](https://help.sap.com/viewer/4505d0bdaf4948449b7f7379d24d0f0d/2.0.02/en-US/54513272339246049bf438a03a8095e4.html).
    Quindi ad esempio: 
    
    "sap-xsenv" **->** "@sap/xsenv"

    var xsjs  = require("sap-xsjs"); **->** var xsjs  = require("@sap/xsjs");

- Il processo di build va effettuando utilizzando il file .jar incluso, con il comando:

    *java -jar MTABUILDER110_0-80002501.JAR --build-target CF --mtar ./target/bookstoremta.mtar build*

- Il deploy su CF va effettuato con [l'interfaccia da linea di comando di CF](https://docs.cloudfoundry.org/cf-cli/), con l'aggiunta del [plugin per MTA](https://github.com/SAP/cf-mta-plugin). I comandi usati sono:
    
    *cf login* per effettuare il login dell'account di CF

    *cf deploy bookstoremta.mtar* per il deploy.


# (Original) MTA-BookStore
BookStore app with MTA (multiple target application) concept
You can read more info about the app in the following blog post: 
https://blogs.sap.com/2017/05/11/develop-a-full-stack-application-for-cf-using-sap-web-ide/
