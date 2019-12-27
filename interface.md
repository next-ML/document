## Dataset对象

URL： */< string:user_id >/dataset/< string:dataset_name >*



**POST方法**

上传一个数据集。

文件数据流放在http的file下。

数据集文件类型支持：csv。

返回该数据集的元数据，格式参见DatasetMeta对象的GET方法。



**GET方法**

获取一个数据集的数据内容。

返回数据集的内容本身，格式示例如下：

{

​	"data": [

​		["1", 2019, 30.5],

​		["2", 2018, 50.3],

​		["3", 2020, 19.0],

​	]

}



## DatasetMeta对象

URL：*/< string:user_id >/dataset/< string:dataset_name >/meta*



**POST方法**

生成一个数据集文件的元数据。

返回该数据集的元数据，格式参见DatasetMeta对象的GET方法。



**GET方法**

获取一个数据集文件的元数据。

返回该数据集的元数据。示例如下：

{

​	"name": "iris",

​	"size": 153683,

​	"num_rows": 163,

​	"columns":[

​		{

​			"name": "length",

​			"dtype": "numeric",

​			"type": "float"

​		},

​		{

​			"name": "class",

​			"dtype": "category",

​			"type": "object"

​		}

​	]

}



## TrainingConfig对象

URL：*/< string::user_id >/training_config/< string:task_name >*



POST方法：

附带的上传数据示例：

{

​	"user_id":"guest",

​	"dataset_name":"iris.csv",

​	"model_type":"classification",

​	"label_columns":["specis"],

​	"feature_columns":["width","height"],

​	"time_limit":120,

​	"max_trial":100

}



GET方法：

返回数据与POST方法一致。



## EvaluationTask对象

