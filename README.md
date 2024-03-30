# TP-4: Functores y polimorfismo

## Pre-requisitos

Tener instalado [prolog](https://github.com/pdep-utn/enunciados-miercoles-noche/blob/master/pages/prolog/entorno.md).

## El enunciado: Elecciones
Se avecina una reñida elección entre el Partido Conversador y el Partido Vertical; las autoridades electorales nos contrataron para programar un sistema que procese la información que tenemos de los partidos y sus afiliados.

### Base de conocimientos
Conocemos los nombres y provincias de residencia de los afiliados a partidos políticos:
<u>Partido Conversador</u>
- Dante: vive en Mendoza.
- Juan: vive en CABA.
- Tomi: vive en Córdoba.
- Juani: vive en Córdoba.
<u>Partido Vertical:</u>
- Emi: vive en La Rioja.
- Manu: vive en Córdoba.
- Aye: vive en La Rioja.
- Feche: vive en La Rioja.

En la próxima elección, se votarán candidatos para los cargos de presidente y diputados. Las candidaturas presentadas ante las autoridades son las siguientes:
- Presidente: Juan, Emi.
- Diputado por La Rioja: Dante, Aye.
- Diputado por Córdoba: Tomi, Juani, Manu.
- Diputado por CABA: Feche.

Con esta información, queremos desarrollar predicados inversibles que nos permitan consultar la siguiente información:

1. Rivales
Dos personas son rivales si se postulan para el mismo cargo (en el caso de las candidaturas a diputados, esto incluye las provincias por las que se postulan).
_Por ejemplo, Dante y Aye son rivales; Tomi y Juani también._

2. Listas en provincias
Queremos saber, dada una provincia y un candidato, si el candidato aparecerá en las listas de esta provincia. Los candidatos a presidente se presentan a nivel nacional, por lo tanto aparecerán en las listas de todas las provincias.
_Por ejemplo, en las listas de Córdoba aparecerán Juan, Tomi, Juani, Emi y Manu._

3. Elecciones sin competencia
Se considera que no hay competencia para cierto cargo si solamente hay una candidatura para el mismo.
_Por ejemplo, no hay competencia para el cargo de diputado por CABA._

4. Internas
Se considera que cierto partido tiene una interna para cierto cargo si hay varias candidaturas para el mismo cargo correspondientes al mismo partido.
_Por ejemplo, el P. Conversador tiene una interna para el cargo de diputado por Córdoba._

5. Mudanzas
Se considera que un candidato se tendría que mudar a cierto distrito si vive en un distrito distinto de aquel en el que tendría que residir de ser electo. El presidente debe residir en CABA, y los diputados, en las provincias por las cuales fueron electos.
_Por ejemplo, Dante tendría que mudarse a La Rioja, dado que vive en Mendoza pero es candidato a diputado por La Rioja. A su vez, Emi tendría que mudarse a CABA dado que es candidato a presidente y vive en La Rioja. En cambio, Juan no debe mudarse (candidato a presidente, ya vive en CABA), y tampoco debe hacerlo Aye (candidata a diputada por La Rioja, ya vive allí)._

6. Permisos para acceder
Sabemos que los partidos poseen sedes. Existen dos tipos de sedes: comités y oficinas; estas últimas están a cargo de una persona:
- El Partido Conversador posee un comité llamado “Honor conversador”,
- El Partido Vertical posee un comité llamado “Legado vertical”,
- El Partido Vertical posee una oficina a cargo de Emi llamada “La Emicueva”.
- El Partido Conversador posee una oficina a cargo de Aye llamada “La inaccesible”.
Un candidato puede acceder a un comité si está afiliado al partido al cual pertenece. Si es una oficina, además tiene que ser el dueño de la misma.
_Por ejemplo, Dante puede acceder a “Honor conversador” y Emi a “La Emicueva”. Curiosamente, como “La inaccesible” está registrada como del Partido Conversador, pero está a nombre de Aye (afiliada al Partido Vertical), nadie puede acceder._
