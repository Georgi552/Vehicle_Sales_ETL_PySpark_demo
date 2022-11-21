# Vehicle_Sales_ETL_demo
Databricks notebook project demo of etl process in python and pyspark 

To view the DataBricks notebook download the HTML file and open it in browser oc chek the code in the .py file.
PDF visualization of the notebook is also provided.

Requirementns:
This code is executed in Databricks Notebook, SparkSession is automaticly imported and builded.

import pandas as pd
import numpy as np
from pyspark.sql.functions import col, sum
from matplotlib import pyplot as plt 

This project uses publick data from https://data.egov.bg/
The data in csv format is downloaded in uploaded in Azure Blob storage.
The Blob Storage is mounted in Databricks.

ETL Steps:
The code is following ETL model. 
In the class initialization step the class can be called with differenт parameterns for diplaying different desired results.

Available params:

1."col_type" represents "ВИД МПС"
it can be one of the following:

+--------------------+
| СПЕЦИАЛЕН АВТОМОБИЛ|
|             АВТОБУС|
|   ТОВАРЕН АВТОМОБИЛ|
|             КОЛЕСАР|
|    МОТОЦИКЛЕТ С КОШ|
|       ЛЕК АВТОМОБИЛ|
|РЕМАРКЕ ЗА ЛЕК АВ...|
|                ОБЩО|
|   СПЕЦИАЛНО РЕМАРКЕ|
|МОТОТРИКОЛКА ТОВАРНА|
|    ЧЕТИРИКОЛЕСНО ПС|
|          МОТОЦИКЛЕТ|
|         ПОЛУРЕМАРКЕ|
|РЕМАРКЕ ЗА ТОВАРЕ...|
|              ВЛЕКАЧ|
|             МОТОПЕД|
|МОТОТРИКОЛКА ПЪТН...|
|       ТРИКОЛЕСНО ПС|
+--------------------+
in the demo are used - 
("ЛЕК АВТОМОБИЛ", "ТОВАРЕН АВТОМОБИЛ", "МОТОЦИКЛЕТ")

2. "col_age" "общо-употр_" or "общо-нови"
