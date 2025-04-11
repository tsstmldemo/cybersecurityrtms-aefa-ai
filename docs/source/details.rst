[cybersecurityrtms-aefa-ai] Details
============================

Generated On: 2025-04-11 22:26:42 UTC

TML Solution DAG Parameters' Details: User Chosen Parametets
----------------------------

STEP 1: Get TML Core Params: `tml_system_step_1_getparams_dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_1_getparams_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - solutionname
     - cybersecurityrtms-aefa-ai
   * - solutiontitle
     - Entity-Based Real-Time Advanced Cybersecurity Prevention and Monitoring
   * - solutiondescription
     - TML Real-Time Memory of Sliding Time Windows For Advanced Cybersecurity Prevention
   * - brokerhost
     - 127.0.0.1
   * - brokerport
     - 9092
   * - cloudusername
     - None
   * - ingestdatamethod
     - LOCALFILE
 
STEP 2: Create Kafka Topics: `tml_system_step_2_kafka_createtopic_dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_2_kafka_createtopic_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - companyname
     - Otics
   * - myname
     - Sebastian
   * - myemail
     - Sebastian.Maurice
   * - mylocation
     - Toronto
   * - replication
     - 1
   * - numpartitions
     - 1
   * - enabletls
     - 1
   * - microserviceid
     - 
   * - raw_data_topic
     - iot-raw-data,rtms-stream-mylogs,rtms-stream-mylogs2
   * - preprocess_data_topic
     - iot-preprocess,iot-preprocess2,rtms-preprocess,attacktopic,rtmstopic,patterntopic
   * - ml_data_topic
     - ml-data
   * - prediction_data_topic
     - prediction-data

STEP 3: `Produce to Kafka Topics <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_read_LOCALFILE_step_3_kafka_producetotopic_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - PRODUCETYPE
     - LOCALFILE
   * - inputfile
     - /rawdatademo/cisco_network_data.txt
   * - TOPIC
     - iot-raw-data
   * - PORT
     - _-1
   * - IDENTIFIER
     - TML solution,/rawdatademo/cisco_network_data.txt
   * - HTTPADDR
     - https://
   * - FROMHOST
     - ('seb', '127.0.1.1')
   * - TOHOST
     - 0.0.0.0
   * - CLIENTPORT
     - Not Applicable
   * - TSS_CLIENTPORT
     - Not Applicable
   * - TML_CLIENTPORT
     - Not Applicable
   * - docfolder
     - mylogs,mylogs2
   * - doctopic
     - rtms-stream-mylogs
   * - chunks
     - 3000
   * - docingestinterval
     - 30

STEP 4: Preprocesing Data: `tml-system-step-4-kafka-preprocess-dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_4_kafka_preprocess_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - raw_data_topic
     - iot-raw-data,rtms-stream-mylogs,rtms-stream-mylogs2
   * - preprocess_data_topic
     - iot-preprocess,iot-preprocess2,rtms-preprocess,attacktopic,rtmstopic,patterntopic
   * - preprocessconditions
     - 
   * - delay
     - 70
   * - maxrows
     - 800
   * - array
     - 0
   * - saveasarray
     - 1
   * - topicid
     - -999
   * - rawdataoutput
     - 1
   * - asynctimeout
     - 120
   * - timedelay
     - 0
   * - preprocesstypes
     - anomprob,trend,avg
   * - pathtotmlattrs
     - --pathtotmlattrs--
   * - identifier
     - RTMS Cybersecurity Prevention
   * - jsoncriteria
     - uid=hostName,filter:allrecords~subtopics=hostName,hostName,hostName~values=inboundpackets,outboundpackets,pingStatus~identifiers=inboundpackets,outboundpackets,pingStatus~datetime=lastUpdated~msgid=~latlong=

STEP 4a: Preprocesing Data: `tml-system-step-4a-kafka-preprocess-dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_4a_kafka_preprocess_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - raw_data_topic
     - rtms-pgpt-ai
   * - preprocess_data_topic
     - rtms-pgpt-ai-mitre
   * - preprocessconditions
     - 
   * - delay
     - 70
   * - maxrows
     - 50
   * - array
     - 0
   * - saveasarray
     - 1
   * - topicid
     - -999
   * - rawdataoutput
     - 1
   * - asynctimeout
     - 120
   * - timedelay
     - 0
   * - preprocesstypes
     - avg
   * - pathtotmlattrs
     - --pathtotmlattrs1--
   * - identifier
     - Mitre ATTCK
   * - jsoncriteria
     - uid=tactic,filter:allrecords~subtopics=technique,technique,technique~values=FinalAttackScore,FinalPatternScore,RTMSSCORE~identifiers=FinalAttackScore,FinalPatternScore,RTMSSCORE~datetime=TimeStamp~msgid=Entity,PartitionOffsetFound,NumAttackWindowsFound,NumPatternWindowsFound,SearchEntity,rtmsfolder,CurrentRTMSMAXWINDOW~latlong=

STEP 4b: Preprocesing Data: `tml-system-step-4b-kafka-preprocess-dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_4b_kafka_preprocess_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - raw_data_topic
     - --raw_data_topic2--
   * - preprocess_data_topic
     - --preprocess_data_topic2--
   * - preprocessconditions
     - --preprocessconditions2--
   * - delay
     - --delay2--
   * - maxrows
     - --maxrows2--
   * - array
     - --array2--
   * - saveasarray
     - --saveasarray2--
   * - topicid
     - --topicid2--
   * - rawdataoutput
     - --rawdataoutput2--
   * - asynctimeout
     - --asynctimeout2--
   * - timedelay
     - --timedelay2--
   * - preprocesstypes
     - --preprocesstypes2--
   * - pathtotmlattrs
     - --pathtotmlattrs2--
   * - identifier
     - --identifier2--
   * - jsoncriteria
     - --jsoncriteria2--

STEP 4c: Preprocesing Data: `tml-system-step-4c-kafka-preprocess-dag  <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_4c_kafka_preprocess_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - raw_data_topic
     - iot-preprocess
   * - preprocess_data_topic
     - rtms-preprocess
   * - delay
     - 70
   * - maxrows
     - 100
   * - array
     - 0
   * - saveasarray
     - 1
   * - topicid
     - -999
   * - rawdataoutput
     - 1
   * - asynctimeout
     - 120
   * - timedelay
     - 0
   * - searchterms
     - rgx:p([a-z]+)ch ~~~ |authentication failure,--entity-- password failure
   * - rtmsstream
     - rtms-stream-mylogs
   * - identifier
     - RTMS Past Memory of Events
   * - rememberpastwindows
     - 500
   * - patternwindowthreshold
     - 30
   * - localsearchtermfolder
     - |mysearchfile1,|mysearchfile2
   * - localsearchtermfolderinterval
     - 0
   * - rtmsscorethreshold
     - 0.6
   * - rtmsscorethresholdtopic
     - rtmstopic
   * - attackscorethreshold
     - 0.6
   * - attackscorethresholdtopic
     - attacktopic
   * - patternscorethreshold
     - 0.6
   * - patternscorethresholdtopic
     - patterntopic
   * - rtmsfoldername
     - rtms2
   * - rtmsmaxwindows
     - 1000000
   * - RTMS Output Github Link
     - `Output Data URL <https:\/\/github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/rtms2>`_

STEP 5: Entity Based Machine Learning : `tml-system-step-5-kafka-machine-learning-dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_5_kafka_machine_learning_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - preprocess_data_topic
     - iot-preprocess,iot-preprocess2,rtms-preprocess,attacktopic,rtmstopic,patterntopic
   * - ml_data_topic
     - ml-data
   * - modelruns
     - --modelruns--
   * - offset
     - -1
   * - islogistic
     - --islogistic--
   * - networktimeout
     - --networktimeout--
   * - modelsearchtuner
     - --modelsearchtuner--
   * - processlogic
     - --processlogic--
   * - dependentvariable
     - --dependentvariable--
   * - independentvariables
     - --independentvariables--
   * - rollbackoffsets
     - --rollbackoffsets--
   * - topicid
     - -999
   * - consumefrom
     - rtms-preprocess
   * - fullpathtotrainingdata
     - --fullpathtotrainingdata--
   * - transformtype
     - --transformtype--
   * - sendcoefto
     - --sendcoefto--
   * - coeftoprocess
     - --coeftoprocess--
   * - coefsubtopicnames
     - --coefsubtopicnames--
   * - ML Output Github Link
     - `Output Data URL <--mloutputurl-->`_

STEP 6: Entity Based Predictions: `tml-system-step-6-kafka-predictions-dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_6_kafka_predictions_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - preprocess_data_topic
     - iot-preprocess,iot-preprocess2,rtms-preprocess,attacktopic,rtmstopic,patterntopic
   * - ml_prediction_topic
     - --ml_prediction_topic--
   * - streamstojoin
     - --streamstojoin--
   * - inputdata
     - --inputdata--
   * - consumefrom
     - --consumefrom2--
   * - offset
     - -1
   * - delay
     - 70
   * - usedeploy
     - --usedeploy--
   * - networktimeout
     - --networktimeout--
   * - maxrows
     - 800
   * - topicid
     - -999
   * - pathtoalgos
     - --pathtoalgos--

STEP 7: Real-Time Visualization: `tml-system-step-7-kafka-visualization-dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_7_kafka_visualization_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - vipervizport
     - 49689
   * - topic
     - rtms-pgpt-ai-mitre
   * - dashboardhtml
     - dashboard-rtms-ai-mitre.html
   * - secure
     - 1
   * - offset
     - -1
   * - append
     - 0
   * - chip
     - amd64
   * - rollbackoffset
     - 400

STEP 8: `tml_system_step_8_deploy_solution_to_docker_dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_8_deploy_solution_to_docker_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^
.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - Docker Container
     - --dockercontainer--
   * - Docker Run Command
     - --dockerrun--

STEP 9: `tml_system_step_9_privategpt_qdrant_dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_9_privategpt_qdrant_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^
.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - PrivateGPT Container
     - maadsdocker/tml-privategpt-with-gpu-nvidia-amd64-v2
   * - PrivateGPT Run Command
     - docker run -d -p 8001:8001 --net=host --gpus all -v /var/run/docker.sock:/var/run/docker.sock:z --env PORT=8001 --env TSS=0 --env GPU=1 --env COLLECTION=tml-llm-model-v2 --env WEB_CONCURRENCY=2 --env CUDA_VISIBLE_DEVICES=0 --env TOKENIZERS_PARALLELISM=false --env temperature=0.1 --env vectorsearchtype="Manhattan" --env contextwindowsize=4096 --env vectordimension=768 maadsdocker/tml-privategpt-with-gpu-nvidia-amd64-v2
   * - Qdrant Container
     - qdrant/qdrant
   * - Qdrant Run Command
     - docker run -d -p 6333:6333 -v $(pwd)/qdrant_storage:/qdrant/storage:z qdrant/qdrant
   * - Consumefrom
     - rtms-preprocess
   * - pgpt_data_topic
     - rtms-pgpt-ai
   * - offset
     - -1
   * - rollbackoffset
     - 400
   * - topicid
     - -999
   * - enabletls
     - 1
   * - partition
     - -1
   * - prompt
     - [INST] Are there any errors or suspicious activity in the log messages found? Give a detailed response, and any resolutions that need to be done. Also, Can you give me the MITRE ATT&CK tactic and technique classification for these messages?[/INST]
   * - context
     - This data are from network log files. This log file data have been filtered using the search terms shown in the messages. The filtered messages may indicate potential suspicious log entries that could indicate a cyber attack.
   * - jsonkeytogather
     - SearchTextFound
   * - keyattribute
     - 
   * - keyprocesstype
     - 
   * - vectordbcollectionname
     - tml-llm-model-v2
   * - concurrency
     - 2
   * - CUDA_VISIBLE_DEVICES
     - 0
   * - pgpthost
     - http://127.0.0.1
   * - pgptport
     - 8001
   * - hyperbatch
     - 0
   * - docfolder
     - --docfolder--
   * - docfolderingestinterval
     - 900
   * - useidentifierinprompt
     - 1
   * - searchterms
     - --searchterms--
   * - streamall
     - 1
   * - temperature
     - 0.1
   * - vectorsearchtype
     - Manhattan
   * - llm
     - Refer to: https://tml.readthedocs.io/en/latest/genai.html
   * - embedding
     - Refer to: https://tml.readthedocs.io/en/latest/genai.html
   * - vectorsize
     - Refer to: https://tml.readthedocs.io/en/latest/genai.html
   * - contextwindowsize
     - 4096
   * - vectordimension
     - 768
   * - mitrejson
     - /rawdata/mitre.json

STEP 10: `tml_system_step_10_documentation_dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_10_documentation_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^
.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - Solution Documentation URL
     - https://cybersecurityrtms-aefa-ai.readthedocs.io
