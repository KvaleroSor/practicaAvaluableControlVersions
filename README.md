# Pràctica Avaluable Sistemes de Controls de Versions 2nd CFGS Semipresencial DAW - Kike Valero

### Introducció teòrica de què és Git.

    Git és un "Sistema de control de versions distribuit" açò què significa, açò significa que si clonem 
    un repositori remot en la nostra area local què ens va a permetre treballar bé siga amb connexió com 
    sense connexió i de forma totalment remota, sense afectar el nostre codi al codi font o dels 
    nostres companys.
    Una vegada hem fet tot el què devien fer amb el codi confirmem de forma local els canvis realitzats i 
    a continuació sincronitzem la copia del nostre repositori local amb el servidor remot. Fer-ho d´aquesta 
    forma va a permetrems vore diferencies amb codi de companys o amb el codi font i poder avaluar que canvis 
    interessen implementar i quins no, alguns del canvis podrien ser errates que gràcies al sistema que 
    implementa Git és pot avaluar abans de canviar el codi font.

    ####Característiques de Git.

        - Rames.
        - Confirmacions d´arxius.
        - Desenvolupament simultani.
        - Integració incorporada. 

### Metodologia Git Flow.

    La metodologia Git Flow com nomenàvem abans en les característiques de Git, es una estructura de rames que 
    facilita la gestió, organització i desenvolupament dels nostres projectes. Per dir-ho d´alguna manera, 
    "Es una forma de tindre ordenat el desorde". 

    No deixa de ser un patró estandar, la qual cosa fa que siga més fàcil d´interpretar per tots, siga la companyia
    que siga i el projecte que siga.
    
    Esta es basa en una estructura de rames les quals son: 

        - Main --> Rama en la qual estarà desplegat el codi en producció.
        - Develop --> Rama en la qual estarà integrat el codi més recent què és preparà per passar-lo a producció.
        - Feature --> Rama per a desenvolupar noves funcionalitats.
        - Release --> Rama on és prepara i s´estabilitza una versió abans de passar-la.
        - Hotfix --> Rama què on és fan solucions ràpides per a problemes que sorgixen en producció.
        - Support --> Rama per donar suport a versions més antigues o especifiques.

### Perquè la utilitzem en el nostre desenvolupament.

    L´utilitzem en el nostre desenvolupament perquè és una forma molt neta de tindre el codi organitzat, i de 
    tindre una molt bona trazabilitat de la evolució del nostre codi, ja que en tot moment és pot fer seguiment del 
    mateix, dels **camins que ha tingut** i de qui és l´autor que ho ha desenvolupat. 
    
    Per a projects xicotets pot ser no siga extremadament avantatjós, però quan parlem de projectes grans, on es veuen 
    involucrades moltes persones, és la millor opció, no obstan, siga avantatjós o no, va a deixar-nos una estructura de 
    projecte molt fàcil d´interpretar i de seguir per si a futur d´altres persones què no han estat en un principi en la 
    creació de dit projecte necessiten treballar sobre ell.


## Explicació detallada del procés realitzat.

    ![Image exemple]("./CA01--CAPTURA_PANTALLA-1/1- creant repo.png")

    






