Este repositorio contiene el proyecto completo para predecir qué clientes del banco podrían darse de baja en los próximos meses. El foco estuvo en predecir la clase BAJA+2, es decir, clientes que se darán de baja dentro de los 30-60 días. 
El modelo se entrenó con datos históricos, se optimizó mediante búsqueda bayesiana, y se evaluó usando curvas de ganancia simulando el envío de estímulos comerciales.

Para buscar encontrar el mejor modelo, me limité a ejecutar el notebook "WorkFlow_01.ipynb" realizando pequeñas modificaciones entre corrida y corrida, creando una carpeta distinta para almacenar cada resultado.

Me enfoqué en probar diferentes técnicas para imputar valores los faltantes de las variables "rotas". Las carpetas "WF7XXX" contienen los resultados de dichas corridas.

Reconozco que cometí el error de no guardar adecuadamente los resultados de mis pruebas relacionadas con data drifting. No estoy todavía habituado a llevar estos experimentos de manera metódica, y lo ideal hubiera sido tener un notebook separado para cada tipo de prueba. 
En su momento intenté ajustar los datos mediante el IPC para corregir posibles efectos de inflación, pero los resultados del modelo se desplomaban. 

Dado que el dataset no contaba con muchos períodos históricos, finalmente tomé la decisión de entrenar siempre con todos los meses disponibles previos al mes objetivo.

Entrené modelos usando LightGBM y realicé la búsqueda de hiperparámetros con mlrMBO. Una vez encontrados los mejores parámetros, volví a entrenar usando todos los meses disponibles antes de la predicción.
