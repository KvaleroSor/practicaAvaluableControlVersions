# Pràctica Avaluable Sistemes de Controls de Versions 2nd CFGS Semipresencial DAW - Kike Valero

### Introducció teòrica de què és Git.

    Git és un "Sistema de control de versions distribuit" açò què significa, açò significa que si clonem
    un repositori remot en la nostra area local què ens va a permetre treballar bé siga amb connexió com
    sense connexió i de forma totalment remota, sense afectar el nostre codi al codi font o dels
    nostres companys.

    Una vegada hem fet tot el què deviem fer amb el codi confirmem de forma local els canvis realitzats i
    a continuació sincronitzem la copia del nostre repositori local amb el servidor remot. Fer-ho d´aquesta
    forma va a permetrems vore diferencies amb codi de companys o amb el codi font i poder avaluar que canvis
    interessen implementar i quins no, alguns del canvis podrien ser errates que gràcies al sistema que
    implementa Git és pot avaluar abans de canviar el codi font.

#### Característiques de Git.

        - Branques.
        - Confirmacions d´arxius.
        - Desenvolupament simultani.
        - Integració incorporada.

### Metodologia Git Flow.

    La metodologia Git Flow com nomenàvem abans en les característiques de Git, es una estructura de branques que
    facilita la gestió, organització i desenvolupament dels nostres projectes. Per dir-ho d´alguna manera,
    "Es una forma de tindre ordenat el desorde".

    No deixa de ser un patró estandar, la qual cosa fa que siga més fàcil d´interpretar per tots, siga la companyia
    que siga i el projecte que siga.

    Esta es basa en una estructura de branques les quals son:

        - Main -> Rama en la qual estarà desplegat el codi en producció.
        - Develop -> Rama en la qual estarà integrat el codi més recent què és preparà per passar-lo a producció.
        - Feature -> Rama per a desenvolupar noves funcionalitats.
        - Release -> Rama on és prepara i s´estabilitza una versió abans de passar-la.
        - Hotfix -> Rama què on és fan solucions ràpides per a problemes que sorgixen en producció.
        - Support -> Rama per donar suport a versions més antigues o especifiques.

### Perquè la utilitzem en el nostre desenvolupament.

    L´utilitzem en el nostre desenvolupament perquè és una forma molt neta de tindre el codi organitzat, i de
    tindre una molt bona trazabilitat de la evolució del nostre codi, ja que en tot moment és pot fer seguiment del
    mateix, dels **camins que ha tingut** i de qui és l´autor que ho ha desenvolupat.

    Per a projects xicotets pot ser no siga extremadament avantatjós, però quan parlem de projectes grans, on es veuen
    involucrades moltes persones, és la millor opció, no obstan, siga avantatjós o no, va a deixar-nos una estructura de
    projecte molt fàcil d´interpretar i de seguir per si a futur d´altres persones què no han estat en un principi en la
    creació de dit projecte necessiten treballar sobre ell.

## Explicació detallada del procés realitzat.

### Tasques Usuari 1:

#### Creació del repositori: practicaAvaluableControlVersions.

És crea el repositori remot en GitHub on volem iniciar el nostre projecte, s´afegeix el nom i l´arxiu README.md.

![Creació repositori](./CA01--CAPTURA_PANTALLA-1/1-creantrepo.png)

#### Clonant el repositori remot en l´area local.

És clona el repositori remot en l´area local on anem a treballar amb ell.

    - Comando utilitzat:

        - git clone <url del repositori remot>

![Clonació repositori](./CA01--CAPTURA_PANTALLA-1/2-%20clonant%20repo.png)

#### Creant branca develop i push de la branca develop al repositori remot.

És crea la branca develop del projecte.
És fa push al repositori remot per afegir els canvis.

    - Comandos utilitzats:

        - git checkout -b <nom de la branca (develop) en el nostre cas>
        - git push origin <nom de la branca (develop) en el nostre cas>

![Creació i push branca develop](./CA01--CAPTURA_PANTALLA-1/3-%20creant%20rama%20develop%20i%20push.png)

#### Afegint la codi inicial del projecte "boilerplate" a la branca develop.

En aquest cas s´ha utilitzat una "boilerplate" per donar-nos
un codi font base del projecte.

    - Comandos utilitzats:

        - git add <nom del directori on es troba la "boilerplate">
        - git commit (afegim un missatge amb la següent estructura:

            * Nom d´usuari - Títol del commit.

            * Breu descripció del que s´ha fet a la modificació.)

![Afegint codi inicial a develop](./CA01--CAPTURA_PANTALLA-1/4-%20afegint%20part%20inicial%20projecte%20amb%20push%20develop.png)

#### Missatge de commit inicial a develop. (Explicació de l´estructura en el punt anterior).

![Missatge commit inicial develop](./CA01--CAPTURA_PANTALLA-1/5-%20missatge%20commit%20develop%20inicial.png)

#### Metodologia GitFlow. Creació de les branques "feature", "release" i "Hoffix" i push de les mateixes.

És creen les branques "feature", "release" i "hotfix" al repositori local i es fa un push
per pujar-les al repositori remot, de tal forma què estiguen disponibles per a la resta
de companys.

    - Comandos utilitzats:

        * git checkout -b feature.
        * git checkout -b release.
        * git checkout -b hotfix.
        * git push origin features.
        * git push origin release.
        * git push origin hotfix.

![Creació branques](./CA01--CAPTURA_PANTALLA-1/6-%20creant%20rames%20features%20release%20hotfix%20i%20push.png)

#### Resum de les branques creades i afegides al repositori remot.

La branca support no s´ha afegit perquè el projecte es desenvolupa desde 0 i com es una branca
que dona support a versions més antigues i especifiques no s´ha creat de moment.

    - Comandos utilitzats:

        * git branch.

![Resum branques creades](./CA01--CAPTURA_PANTALLA-1/7-%20resum%20branques.png)

#### Creació del "hotfix/milloresV_1_0".

L´usuari 1 crea un "hotfix/milloresV_1_0" per realitzar millor al codi que ha creat
l´usuari 2.

L´usuari 1 es porta les branques que ha utilitzat l´usuari 2 per poder fer desprès la
fusió dels canvis.

Una vegada disposa del codi que ha creat l´usuari 2 a la branca "hotfix/milloresV_1_0"
efectua els canvis que considera oportuns.

Finalitzats el canvis fusiona la branca "hotfix/milloresV_1_0" amb les branques que havia
modificat l´usuari 2 | feature/contingutsHTML | feature/atributsHTML.

    - Comandos utilitzats:

        * git checkout -b hotfix/milloresV_1_0.
        * git checkout -b feature/contingutHTML origin/feature/contingutHTML.
        * git checkout -b feature/atributsHTML origin/feature/atributsHTML.
        * git checkout hotfix/milloresV_1_0. (Per situarse a la branca hotfix).
        * git merge feature/contingutHTML.
        * git merge feature/atributsHTML.

Si en el procés de fusionar les diverses branques hi trobem algún conflicte, el resolguem de
forma manual al editor i actualitzem l´arxiu afegint-lo al stage i fent un commit del mateix.

![Millora 1](./CA01--CAPTURA_PANTALLA-1/9-%20definim%20millores.png)

![Millora 1](./CA01--CAPTURA_PANTALLA-1/10-%20definim%20millores%202.png)

![Creació hotfix/milloresV_1_0](./CA01--CAPTURA_PANTALLA-1/8-%20creem%20branca%20hotfix%20i%20merge%20del%20usuari%202.png)

#### Missatge del commit de les millores.

![Missatge commit millores aplicades](./CA01--CAPTURA_PANTALLA-1/11-%20missatge%20commit%20millores.png)

### Observacions.

És podrà vore al repositori remot que hi ha dos col·laboradors, son la mateixa persona, es a dir, jo.

Abans de començar el curs gastava un altre usuari de git per a iniciar-me en la tecnologia ja què la
conec de fa alguns anys però fins hores d´ara no sabia gastar-la "com es degut".

Tenia el git configurat amb eixe usuari i email, més avant ja entrats en el curs vaig decidir
crear-me´n un altre conter de git per tindre un un poc mes "professional" amb els coneiximents què anava
a adquirir al curs.
He tornat a configurar l´usuari i el email i ho adjunte per evitar que hi hagen confusions.

![usuari git antic](./CA01--CAPTURA_PANTALLA-1/12-%20justificant%20canvi%20d´usuari%20a%20git.png)
![usuari git nou](./CA01--CAPTURA_PANTALLA-1/13-%20justificant%20canvi%20d´usuari%20a%20git%202.png)

### Tasques Usuari 2:

#### Clonant repositori en el directori del Usuari 2.

És clona el repositori remot en l´area local on anem a treballar amb ell.

    - Comando utilitzat:

        - git clone <url del repositori remot>

![clonacio repositori usuari 2](./CA02--CAPTURA_PANTALLA-2/1-%20clonant%20repositori.png)

#### Creant la branca develop en local i és porta el contingut de la branca origin/develop.

És crea la branca develop en local és porta desde el repositori remot el contingut de la
branca develop.
Per assegurar-se de què la branca develop és queda actualitzada fem un pull a la branca origin.

    - Comando utilitzats:

        - git checkout -b develop origin/develop.
        - git pull origin develop.

![creant i duguent develop de origin](./CA02--CAPTURA_PANTALLA-2/2-%20descarregant%20repo%20de%20rama%20develop%20a%20local%20develop.png)

#### Creació de les branques feature.

És creen les branques "feature/contingutHTML" i "feature/atributsHTML" per tal de fer
les modificacions pertinents als arxius que ho requerisquen.

    - Comandos utilitzats:

        * git checkout -b feature/contingutsHTML.
        * git checkout -b feature/atributsHTML.

![creació branques feature](./CA02--CAPTURA_PANTALLA-2/3-%20creacio%20branques%20feature.png)

#### Afegint l´arxiu contingutsHTML.

La branca "feature/contingutsHTML" s´encarrega de crear a la barra de navegació
de l´arxiu "index.html" un accés a una nova pàgina anomenada "Modificacions continguts
HTML".
També es crea dit arxiu amb el seu contingut.

És fa commit i push de la mateixa per pujar les modificacions a la branca
feature/contingutHTML del repositori remot.

    - Comandos utilitzats:

        * git add <nom del arxiu/directori on shan fet les modificacions>.
        * git commit (afegim un missatge amb la següent estructura:

            * Nom d´usuari - Títol del commit.

            * Breu descripció del que s´ha fet a la modificació.)
        * git push origin feature/contingutsHTML.

![afegint contingutsHTML](./CA02--CAPTURA_PANTALLA-2/4-%20usuari%202%20afegint%20continguthtml%20i%20commit.png)
![afegint contingutsHTML](./CA02--CAPTURA_PANTALLA-2/5-%20push%20feature:contingutHTML.png)

#### Afegint l´arxiu contingutsHTML.

La branca "feature/atributsHTML" s´encarrega de crear a la barra de navegació de l´arxiu
"index.html" un accés a una nova pàgina anomenada "Modificacions atributs HTML".
També es crea dit arxiu amb el seu contingut.

És fa commit i push de la mateixa per pujar les modificacions a la branca
feature/atributsHTML del repositori remot.

    - Comandos utilitzats:

        * git add <nom del arxiu/directori on shan fet les modificacions>.
        * git commit (afegim un missatge amb la següent estructura:

            * Nom d´usuari - Títol del commit.

            * Breu descripció del que s´ha fet a la modificació.)
        * git push origin feature/atributsHTML.

![afegint atributsHTML](./CA02--CAPTURA_PANTALLA-2/6-%20usuari%202%20afegint%20atributsHTML%20i%20commit.png)
![afegint atributsHTML](./CA02--CAPTURA_PANTALLA-2/7-%20push%20feature:atributsHTML%20.png)

### Tasques Usuari 3:

#### Clonant repositori en el directori del Usuari 2.

És clona el repositori remot en l´area local on anem a treballar amb ell.

    - Comando utilitzat:

        - git clone <url del repositori remot>

![clonant repositori remot](./CA03--CAPTURA_PANTALLA-3/1-%20clonant%20repo.png)

#### Creant la branca develop en local i és porta el contingut de la branca origin/develop.

És crea la branca develop en local és porta desde el repositori remot el contingut de la
branca develop.
Per assegurar-se de què la branca develop és queda actualitzada fem un pull a la branca origin.

    - Comando utilitzats:

        - git checkout -b develop origin/develop.
        - git pull origin develop.

![creant branca develop](./CA03--CAPTURA_PANTALLA-3/2-%20descarregant%20a%20develop%20desde%20develop.png)

#### Creació la branca feature/estilsCSS.

És crea la branca "feature/estilsCSS" per tal de fer les modificacions pertinents als arxius
que ho requerisquen.

    - Comandos utilitzats:

        * git checkout -b feature/estilsCSS.

![creant branca feature/estilsCSS](./CA03--CAPTURA_PANTALLA-3/3-%20creant%20rama%20feature:estilsCSS%20desde%20develop.png)

#### Afegint l´arxiu estilsCSS.

La branca "feature/estilsCSS" s´encarrega de crear a la barra de navegació de l´arxiu
"index.html" un accés a una nova pàgina anomenada "Modificacions estils CSS".
També es crea dit arxiu amb el seu contingut.

És fa commit i push de la mateixa per pujar les modificacions a la branca
feature/estilsCSS del repositori remot.

    - Comandos utilitzats:

        * git add <nom del arxiu/directori on shan fet les modificacions>.
        * git commit (afegim un missatge amb la següent estructura:

            * Nom d´usuari - Títol del commit.

            * Breu descripció del que s´ha fet a la modificació.)
        * git push origin feature/estilsCSS.

![afegint arxiu estilsCSS](./CA03--CAPTURA_PANTALLA-3/4-%20afegint%20arxius%20estilscss%20al%20repo%20.png)

#### Missatge commmit de l´arxiu estilsCSS.

![missatge commit](./CA03--CAPTURA_PANTALLA-3/5-%20missatge%20commit%20estilscss.png)

#### Creació la branca release/v1.0.

És crea la branca "release/v1.0" per tal de agrupar totes les "features" fetes sobre
el codi font del projecte que es trobava a la branca develop.

Una vegada es fan les modificacions pertinents, l´usuari 3 és el encarregat de
adjuntar dites "features" fetes per etiquetar-les i resoldre possibles conflictes què
puguen eixir.

En conclusió, preparar el codi per quan és decidisca aplicar a producció què estiga
tot com toca.

    - Comandos utilitzats:

        * git checkout -b release/v1.0.

![creant branca release](./CA03--CAPTURA_PANTALLA-3/6-%20creant%20branca%20release:v1.0.png)

#### Creant branques "feature/contingutHTML" i "feature/atributsHTML".

És creen les branques "feature/contingutHTML" i "feature/atributsHTML" desde el
el repositori remot perquè arrastren amb si mateixa l´última actualització
del codi que hi haja a les mateixes branques.

    - Comandos utilitzats:

        * git checkout -b feature/contingutHTML origin/feature/contingutHTML.
        * git checkout -b feature/atributsHTML origin/feature/atributsHTML.

![creant branques feature en release](./CA03--CAPTURA_PANTALLA-3/7-%20creant%20branques%20feature%20al%20usuari%203%20amb%20contingt.png)

#### ## Merge de les branques "feature" a la branca "release".

Si a l´hora de fer el "merge" ens trobem amb conflictes entre diferents arxius
els resolguem desde l´editor.

Per realitzar el "merge" ens situarem en la branca "release".

Una vegada fet el "merge" i resolts els conflictes puguem vore l´estat dels
canvis que hem realitzat.

Si hi han canvis per confirmar, el que farem serà actualitzar el nostre repositori
local per tindre-ho tot com toca abans de pujar-ho a la branca remota.

    - Comandos utilitzats:

        * git merge feature/congtingutsHTML.
        * git merge feature/atributsHTML.
        * git status.
        * git add <nom dels arxius/directoris implicats>
        * git commit (afegim un missatge amb la següent estructura:

            * Nom d´usuari - Títol del commit.

            * Breu descripció del que s´ha fet a la modificació.)
        * git push origin release/v1.0.

#### Merge de "feature/contingutHTML".

![merge feature/contingutHTML](./CA03--CAPTURA_PANTALLA-3/10-%20merge%20feature:contingutHTML.png)

#### Merge de "feature/atributsHTML".

![merge feature/atributsHTML](./CA03--CAPTURA_PANTALLA-3/9-%20merge%20feature:atributeHTML.png)

#### Merge de "feature/estilsCSS".

![merge feature/estilsCSS](./CA03--CAPTURA_PANTALLA-3/11-%20merge%20feature:estilsCSS.png)

#### Resolguent conflicte una vegada fer el "merge".

![resolguent conflicte](./CA03--CAPTURA_PANTALLA-3/8-%20resolguent%20conflicte%20merge.png)

#### Creació de l´etiqueta per a la release.

Per crear la etiqueta de la release haurem de situar-se a la branca de la
mateixa release a la que vullguem crear l´etiqueta. Una vegada situats a la
branca que toca, creem l´etiqueta.

La finalitat de crear una etiqueta per a la release és per tindre-ho identificat,
es suposa que el codi què és troba a la branca release és codi estabilitzat i
preparar per ser llançat a producció, aleshores, necessitem saber en tot moment
de la versió què és tracta, per dur un bon control i seguiment de les modificacions
què s´han anat fent en quines versions han sigut.

Per crear el tag del release ho fem situats a la branca "release".

    - Comandos utilitzats:

        * git tag -a v1.0 "release/v1.0".
        * git push origin v1.0.

![creant tag release](./CA03--CAPTURA_PANTALLA-3/12-%20git%20tag%20amb%20contingut.png)

#### Creació del release.

Una vegada creada el "tag del release" proseguim a crear el mateix "release".

    - Comandos utilitzats:

        * gh release create release/v1.0 --target <nom de la branca (en el nostre cas "release")> --title "<títol de la release> --notes <features que es veuen involucrades en la release>.

![creació release](./CA03--CAPTURA_PANTALLA-3/13-%20creant%20release.png)

#### Contingut de la "release" creada.

![contingut release creada](./CA03--CAPTURA_PANTALLA-3/14-%20contingut%20release.png)
