CFD.PRG

Libreria de clases para generacion del Comprobante Electronico Digital
en Mexico, segun las indicaciones del SAT


NOTA IMPORTANTE #1
A partir de la version 2.4 de esta libreria, el metodo Sellar() de la clase
CFDComprobante valida que el certificado sea valido y este vigente. Si el 
certificado no pasa estas pruebas, el metodo no generara el sello y devolvera
.F., almacenando en la propiedad CFDConf.ultimoError la descripcion de problema.

Se puede obviar esta validacion almacenando .T. en la propiedad CFDConf.modoPruebas


NOTA IMPORTANTE #2
Si esta teniendo problemas con las funciones o metodos que invocan OpenSSL
y su carpeta SSL esta ubicada en una ruta que contiene nombres largos o 
espacios en blanco, puede que el problema se deba a que la creacion de nombres
cortos (8.3) esta desactivada a nivel de Windows.  Por favor, revise en su
Register la clave:

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\FileSystem\NtfsDisable8dot3NameCreation

y asegurese que su valor sea cero. Si esta en "1", haga el cambio y reinicie
su sistema. Si el valor ya estaba en cero o el problema persiste luego de 
cambiarlo a cero, mueva su carpeta SSL a una ruta que no contenga nombres de
mas de 8 caracteters ni contenga espacios en blanco.


NOTA IMPORTANTE #3
La libreria OpenSSL requiere de las librerias de runtime de VC++ 2008, la cual
puede no estar disponible en algunos equipos, causando problemas con el sellado
de los CFDs (y todas las demas funciones de la libreria que dependan de OpenSSL).

Para solucionar este problema, descargue e instale las librerias necesarias desde
este link (cortesia de Carlos Omar Figueroa):

http://www.microsoft.com/downloads/en/details.aspx?familyid=9B2DA534-3E03-4391-8A4D-074B9F2BC1BF&displaylang=en


NOTA IMPORTANTE #4
Para generar la representacion impresa del CFD se utiliza el procedimiento CFDToCursor() para
pasar los nodos del XML a cursores y asi poder reportarlos. Por regla los saltos de linea y
retornos de carro no estan permitidos en un XML, entonces que pasa si hay un concepto en el
comprobante donde sea muy importante mostrar informacion en lineas adicionales sobre todo para
coneptos muy largos donde se desglozan condiciones u otra informaci�n.

Para solucionar este problema se incluye un parametro adicional a CFDPrint() con el que podemos
indicar que se va a remplazar los conceptos obtenidos por CFDToCursor() en el cursor QCO por los 
que estan en el entorno de datos; aqui se supone que en el entorno de datos tenemos un cursor 
llamado curConceptos con los conceptos del comprobante tal como se guardaron en la base de datos.


***********************************************************
Referencias de Git, GitHub y control de versiones con VFP
***********************************************************
Control de versiones con git y github
-------------------------------------
http://www.slideshare.net/guest638090/control-de-versiones-con-git-y-github


Mini-tutorial Git
-----------------
Muy buena presentaci�n que nos da una idea muy buena de lo que se puede hacer con Git
http://www.slideshare.net/gnrfan/minitutorial-de-git


Getting Started with Git and GitHub on Windows
----------------------------------------------
http://kylecordes.com/2008/git-windows-go


Un tutorial en PDF, medio traducido...
--------------------------------------
http://www.rodolinux.com.ar/docs/Tutorial-de-GIT-Editado.pdf


Uso de la Wiki de GitHub
------------------------
http://www.adictosaltrabajo.com/tutoriales/tutoriales.php?pagina=githubWiki


Primeros pasos con GitHub
-------------------------
http://www.adictosaltrabajo.com/tutoriales/tutoriales.php?pagina=githubFirstStepsUploadProject


An Illustrated Guide to Git on Windows
--------------------------------------
http://nathanj.github.com/gitguide/index.html


TortoiseGit The coolest Interface to (Git) Version Control
----------------------------------------------------------
http://code.google.com/p/tortoisegit/


Curso de Git y GitHub, Fundamentos e Instalaci�n
------------------------------------------------
http://www.illasaron.com/html/content/01-curso-de-git-y-github-fundamentales-e-instalaci%C3%B3n


GitHub Help
-----------
http://help.github.com/win-set-up-git/


Instalar cliente de Git en Windows y conectarse a GitHub
--------------------------------------------------------
http://neurock.com/neurock_blog/2011/07/18/instalar-cliente-git-en-windows-y-conectarse-a-github/


VFP2Text
--------
Add-on for Beyond Compare that allows read-only comparisons of Microsoft Visual FoxPro files. 
http://www.pfsolutions-mi.com/dnn/Downloads/tabid/76/Default.aspx


Beyond Compare
--------------
Herramienta para comparar archivos y carpetas
http://www.scootersoftware.com/download.php


TwoFox
------
Two-way text conversion for VFP files. GenXML converts form, class libraries, etc. into XML files that can easily be handled by version control systems like CVS and SubVersion. For VCX files GenXML generates one XML file for each class letting you create a history for each class and minimizing conflicts. GenCode converts these XML files back into binary files. 
http://foxpert.com/downloads.htm


scXML
-----
El proyecto SCXML trata principalmente de brindar una manera sencilla a los programadores VFP de poder usar un control de versiones con sus Formularios y librer�as VCX.
http://fox.desdeguate.com/scxml/

git community book
------------------
http://book.git-scm.com/

