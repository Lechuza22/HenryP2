<p align="center">
    <img src="https://github.com/user-attachments/assets/5c277d51-711c-4f4a-8c56-3815e747528c" width="25%">
</p>


# README. TP 2. Jerónimo Martinez
Presentación.

Net# es una empresa Uruguaya, con alcance  multinacional, con sedes en: Brasil, Paraguay y chile. NET# es una empresa dedicada al servicio de internet por fibra optica reconocida por la fuerte inversión en esta tecnología y por la velocidad del servicio. A NET# no solo le mueve el hambre comercial sino tambien tienen en cuenta su misión empresarial como una costructura de relaciones, vinculos y negocios mediante el acceso a internet. Por este motivo también incentiva la inclusión mediante el acceso a internet.  

Cabe destacar que NET# esta en pleno auge financiero y organizacional; De manera  que la empresa esta interesada en  llevar el negocio e invertir en Argentina. 
A raiz de esto acude a los datos que proporciona el gobierno sobre telecomunicaciones para conocer la demanda, los competidores, los niveles de acceso a internet y la velocidad de la misma en el territorio. 

Para este trabajo es indispensable la visión y la competencia de un analista de datos, del cual quién escribe, es resonsable del mismo: analizar y transoformar los datos duros, realizar un analisis exploratorio de los datos en base a la demanda de la empresa; y la presentación de un dashboard explicado desde un storytelling que ilustra dicha presentación. 

La finalidad de todo esto es que el negocio sea rentable y se lleve a cabio la misión y visión empresarial.  
Ahora si vamos al trabajo. 

# Tranformación de los datos 
Para más en profundidad el proceoso ver en: Normalización.ipynb

Paso a paso: UItilizamos el archivo internet.xlsx. el cual lo obtuvimos de la página del Ente Nacional de Comunicaciones (ENACOM) de Argentina. La ENACOM es el organismo regulador de las telecomunicaciones en Argentina, responsable de la regulación y control de los servicios de comunicación en el país. 
1. Creamos el archivo Normalización.ipynb, y alli con pandas eliminamos de columnas sin nombres y con datos en null de cada una de las hojas del archivo "Internet.xlsx". 
2. Revisamos las columnas que contienen errores que aparecen en la hoja "acceso por tecnología" y Acc_vel_Loc_sinrango
    - Columna años se reemplazo los errores por el año 2019, siguiendo la lógica de los datos. 
    - Columna Trimestre se reemplazo los errores por el trimestre 4, siguiendo la lógica de los datos. 
    - Columna Velocidad, se reemplazo errores con el valor 6357120, siguiendo la logica de los datos. 
3. Revisamos la hoja dial_baf, en la columna dial_up y registramos algunos datos nulos correspondientes a dos provincias: formosa y misiones. Por logica de los datos y por ser un volumen insignificante decidí revalorar en 0 los datos vacios/null.
4. Pero para una optmización de los recursos y para no ser tan abarcativo decidí eliminar las siguientes tabas: 
- Dial-BAf y Totales Dial-BAf: Estas hojas contienen datos más específicos sobre conexiones dial-up o tecnologías menos utilizadas, que no son tan representativas en un análisis de conectividad actual.
- Totales Accesos por rango y Accesos por rangos: Si bien pueden ofrecer datos útiles, podrían ser redundantes si ya tenemos los datos de velocidad sin rangos y acceso por localidad.

# EDA. La conectividad en la Republica Argentina: inversiones Net#

Aclaración: el desarrollo del EDA se encuentra en el archivo EDA.opynb 

La empresa Net#, multinacional dedicada al servicio de internet por fibra optica esta buscando invertir en Argentina. A raiz de esto acude a los datos que proporciona el gobierno sobre telecomunicaciones.

Las preguntas de las cuales parte la empresa son ¿En qué zonas conviene invertir? ¿Qué acceso existe a internet en dicho pais? ¿Qué tecnologías de comunicación predominan más? ¿Cual es la velocidad que se recomienda implementar? ¿Cuáles son las provicias con mayor demanda y cuales con mayor necesidad de inversión? Todas estas preguntas estan en función al negocio que la empresa tiene en función a futuras e inminentes inversiones.
El analista, quién escribre, entre muchas variables y opciones de analisis decide tomar las siguientes variables: Velocidad, accesos, provincias y tecnologías. A partir de estas variables desarrollará los análisis en los siguientes puntos con sus respectivos análisis/insight. 

1. Resumen estadístico general de velocidad y accesos: análisis de las medidas como la media, mediana, máximo, mínimo y desviación estándar.
2. Análisis de correlación: evaluaré la relación entre las variables numéricas.
3. Distribución de datos Velocidad, Accesos, ADSL, Cablemodem y fibra óptica.
4. Accesos vs Velocidad
5. Distribución de Accesos por Cuartiles de Velocidad
6. Accesos por Tecnología: ADSL, Cablemodem y fibra optica.
7. Valores típicos y comunes: análisis de frecuencias en las variables categóricas y estadísticas en las variables numéricas.
8. Valores inusuales: detección de valores atípicos.
9. Valores faltantes: revisión de la cantidad y ubicación de valores nulos en el conjunto de datos.
10. Acceso total y la velocidad promedio por provincia

Análisis final EDA

- Los usuarios se encuentran en el rango de velocidades bajas debido a limitaciones tecnologicas o economicas. 
- Las tecnologicas adsl cable moden son más estables y la fibra optica parece estar en expanción, pero hay brecha en la infraestructura, que esta en transición. Es decir, en las zonas más densamente probladas y desarrolladas existe más fibra optica que en las rurales. 
- Los usuarios prefieren mayor velocidad y estabilidad: fibra optica es una opción posible. 
- Las velocidades altas estan limitada a regiones (grandes ciudades) o grupo menor de usuarios, mientras que la demanda se ubica en rangos de velocidad baja (esto muestra la falta de inversión)
- Transición de adsl hacia fibra optica (esto se debe a la demanda en velocidad y al desarrollo de las ciudades)
- Los usuarios estan dispuestos a pagar más por más velocidad, hay más demanda en velocidades más rapidas, como ofrece la fibra optica. 
- Las zonas, o provincias de mayor urbanización e infraestructura (Buenos Aires, Córdoba, Entre Rios) son las que presentan más demanda y una oportunidad de inversión más optima. Puede pasar que en estas provincias con más demanda tambien haya más competencia que en las que son menos urbanizadas. 

El EDA tambien ofrece una propuesta de inversión, la cual sugiere una inversión tanto en el servicio de internet por fibra optica, debido a su velocidad, como a la infraestructura de dicha tecnología. 

# Visualización: PowerBi

El Dashboard o visualización de powerBI implica un analisis narrativo de los datos a fin de mostrar la viabilidad del negocio de la instalación de fibra óptica el servicio de internet. Un KPI (Key Performance Indicator o Indicador Clave de Desempeño) es una métrica cuantificable que se utiliza para medir el éxito de una organización en alcanzar los objetivos propuestos: visualizar la inversión en fibra optica. 
El dashboard presenta varias filminas. La primera es un panel que describe cada una de las filminas que incluye los KPIs y los gráficos:

- KPI 1:Aumento del acceso a Internet en un 2% para el próximo trimestre en cada provincia
Este KPI nos permite proyectar la demanda de acceso a internet para el proximo trimestre. Esto nos ayuda a visualizar donde sería rentable la inversión en función a la demanda proyectada. 
- Acceso por provincia en el 2do Trimestre 2024. Esta medida nos siver visualizar el porcentaje que existe de accesos por provincia de modo de que veamos qué provincia tiene mayor demanda respecto a su pobrlación. Además el análisis del porcentaje de accesos por provincia permite tomar decisiones informadas y estratégicas como inversor en telecomunicaciones. Desde la expansión de infraestructura hasta el diseño de estrategias de mercado, esta métrica es esencial para maximizar el retorno de inversión y aprovechar las oportunidades en mercados desatendidos.
- Velocidad promedio por provincia.
Este grafico nos prermite visualizar filtradamente por provincia el promedio de velocidad de internet. Esto tiene una correlación directa con el tipo de tecnología que se usa y predomina en cada provincia, lo cual nos hace conocer tanto la oferta que existe, la exigencia de la demanda y la competencia en empresas de telecomunicación. Como podemos ver, son las provincias más desarrolladas y con más volumen de población las qué tienen y demandan más velocidad. 
- Acceso de tecnología por provincia. 
Este grafico nos muestra filtradas las tecnologías disponibles y las provincias con sus respectivos accesos. El gráfico nos permite visualizar qué tecnología potencialmente será redituable en función a la demanda existente. La fibra optica es una muy buena opción. 
- KPI 2: porcentaje de cobertura  que cuentan con cobertura de fibra óptica por provincias.
Este KPI nos permite: Identificar brechas: Provincias con baja cobertura de fibra óptica pueden ser priorizadas para la expansión del servicio.
También nos permite medir el progreso y Verificar cómo cambia la cobertura a medida que se implementa fibra óptica en nuevas localidades.
Y sobre todo nos permite tomar decisiones estratégicas, es decir, ayudar a los equipos de planificación a enfocar los recursos donde más se necesitan.
- Conclusiones y recomendaciones (final del storyTelling)

# Storytelling: Evaluación del Mercado para la Inversión en Fibra Óptica en Argentina

La empresa uruguaya NET#, líder en fibra óptica a nivel latinoamericano, está explorando oportunidades de expansión en Argentina, un país con un mercado de telecomunicaciones en constante transformación. A través de un análisis exhaustivo, hemos diseñado un dashboard que combina datos clave del acceso a internet, tecnologías disponibles, velocidad de conexión y proyecciones de crecimiento. Este análisis nos permite identificar las áreas estratégicas para maximizar el retorno de inversión y priorizar regiones con mayor potencial para la instalación de infraestructura de fibra óptica. Desarrollaré un capitulo de narración por cada filmina y luego una conclusión final. 

- Capítulo 1: Proyección de Demanda – Una oportunidad de crecimiento sostenido
El primer KPI destaca una proyección del aumento del acceso a internet en un 2% para el próximo trimestre en cada provincia. Este indicador nos brinda una visión sobre la evolución de la demanda, permitiendo identificar regiones donde el crecimiento del acceso puede ser un motor clave para justificar la inversión.
Hallazgo principal: Provincias con baja penetración actual, como Formosa o La Rioja, muestran un potencial significativo para expansión, especialmente si el aumento proyectado se alinea con estrategias de subsidios o promociones iniciales.

- Capítulo 2: Análisis Geográfico – Acceso y Demanda por Provincia
El análisis del porcentaje de acceso por provincia en el segundo trimestre de 2024 resalta una correlación directa entre la penetración del servicio y la densidad poblacional.
Oportunidades destacadas:
Buenos Aires y Córdoba lideran en términos de demanda, pero enfrentan alta competencia.
Provincias emergentes, como Tucumán y Salta, combinan un buen nivel de población con una penetración de mercado más baja, sugiriendo oportunidades de expansión menos saturadas.
Este análisis respalda decisiones estratégicas para priorizar provincias con baja saturación y demanda creciente.

- Capítulo 3: Velocidad Promedio por Provincia – Indicador de Competencia y Demanda
El gráfico de velocidad promedio por provincia revela un panorama claro sobre la calidad del servicio actual:
Provincias desarrolladas, como Buenos Aires, Córdoba y Santa Fe, tienen velocidades promedio más altas, reflejando una mayor demanda de tecnologías avanzadas como fibra óptica.
Provincias periféricas, como Chaco y Formosa, muestran velocidades más bajas, indicando brechas tecnológicas significativas y una oportunidad para posicionar la fibra óptica como una mejora competitiva.
Conclusión clave: Existe una correlación entre las regiones de alta demanda de velocidad y las necesidades insatisfechas de tecnología avanzada, posicionando a NET# como líder en la transformación del mercado.

- Capítulo 4: Tecnología por Provincia – Evaluación de la Infraestructura
El desglose de accesos por tecnología revela la penetración actual de fibra óptica comparada con otras tecnologías como ADSL o redes inalámbricas.
Fibra óptica ya domina en provincias como Buenos Aires, pero su cobertura en regiones como San Juan y La Rioja es limitada, lo que ofrece una oportunidad estratégica para construir infraestructura.
Datos críticos: La infraestructura de fibra óptica tiene un potencial significativo en áreas rurales y semiurbanas donde las tecnologías tradicionales no logran satisfacer las demandas actuales.

- Capítulo 5: Brechas en la Cobertura de Fibra Óptica
El KPI del porcentaje de cobertura de fibra óptica por provincia identifica brechas importantes:
Provincias como Chaco, Jujuy y Formosa tienen una cobertura mínima de fibra óptica, a pesar de contar con una densidad poblacional relevante.
Este KPI permite planificar estratégicamente la expansión, priorizando provincias con alta población no cubierta y un mercado desatendido.
Impacto: Este indicador no solo mide el progreso, sino que también guía la inversión hacia áreas donde NET# puede generar el mayor impacto social y financiero.

-  Conclusión – Donde Invertir y Por Qué
El análisis muestra que las oportunidades de inversión para NET# se encuentran en tres áreas clave:
Mercados emergentes con alta demanda potencial: Provincias como Tucumán, Salta y Santiago del Estero combinan un mercado creciente con una cobertura limitada de fibra óptica.
Reducción de brechas tecnológicas: Regiones periféricas como Formosa y Chaco tienen baja velocidad y limitada infraestructura, ofreciendo un espacio para posicionarse como líder en conectividad avanzada.
Provincias consolidadas con alta competencia: Mientras Buenos Aires y Córdoba ya tienen buena cobertura, la mejora en velocidades y servicios premium puede captar usuarios de empresas rivales.

En resumen, Argentina presenta un terreno fértil para la inversión en fibra óptica. Con el aumento proyectado en el acceso a internet y la creciente demanda de velocidades más altas, NET# puede consolidar su posición como líder en telecomunicaciones a través de:

1.  La expansión en provincias desatendidas.
2.  La mejora de la cobertura en regiones competitivas.
3. La reducción de brechas tecnológicas en zonas rurales y semiurbanas.

La fibra óptica no solo representa una inversión rentable, sino también un puente hacia la inclusión digital en el país.
