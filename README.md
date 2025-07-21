Este repositorio contiene el proyecto completo para predecir qué clientes del banco podrían darse de baja en los próximos meses. El foco estuvo en la clase BAJA+2, es decir, clientes que se darán de baja dentro de los 30 a 60 días.
El modelo se entrenó con datos históricos, se optimizó mediante búsqueda bayesiana y se evaluó usando curvas de ganancia, simulando el envío de estímulos comerciales.

Para encontrar el mejor modelo, fui ejecutando el notebook "WorkFlow_01.ipynb" realizando pequeñas modificaciones entre cada corrida, y guardando los resultados en carpetas separadas.

Me enfoqué principalmente en probar diferentes técnicas de imputación para los valores faltantes de las variables "rotas". Las carpetas WF7XXX contienen los resultados de esas pruebas.

Reconozco que cometí el error de no guardar adecuadamente los resultados de mis pruebas relacionadas con data drifting. Todavía no tengo el hábito de documentar estos experimentos de forma metódica, y lo ideal hubiera sido crear un notebook por cada prueba.
En su momento intenté ajustar los datos con el IPC para corregir efectos de inflación, pero los resultados del modelo se desplomaban.

Los modelos se entrenaron con LightGBM y la búsqueda de hiperparámetros se realizó con mlrMBO. Una vez encontrados los mejores parámetros, volví a entrenar utilizando todos los meses disponibles antes del mes objetivo.
Dado que el dataset no contaba con muchos períodos históricos, finalmente decidí entrenar siempre con todos los meses disponibles previos a la predicción
