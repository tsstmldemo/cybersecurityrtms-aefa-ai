[cybersecurityrtms-aefa-ai] Operating Details
====================================

Generated On: 2025-04-11 22:26:42 UTC

.. note::
   **THIS DOCUMENTATION CREATION WAS AUTOMATICALLY TRIGGERED BY:** TML Solution Container

   If this documentation was triggered by the TSS - then your solution is running in the TSS Development environment.  All ports and links will point to your TSS 
   development environment.

   If this documentation was triggered by your TML solution - then your solution is running in your TML solution container.  All ports and links will point to 
   your TML solution container.

   **If you have NOTHING running - most of the links and ports below WILL NOT WORK.**

   **If you have BOTH RUNNING - all of the links and ports below WILL WORK.**

   Also, this documentation is updated by the **LATEST** run of either the TSS or TML.

.. important::
   These are the operating details for your TML solution.  

   It is important to note that this documentation will 

   dynamically update with the **Runtime Ports** for your solution.

   The ports below were valid for the last run of your solution, and will 

   **not be valid if your [cybersecurityrtms-aefa-ai] container is NOT running**.

.. tip::
   You must have your [cybersecurityrtms-aefa-ai] container running before connecting to the Visualization and Airflow URLs.

Github Logs
----------
This is your main TSS Github logs.  All TSS processes are committed to Github and logged. 

.. important::
   https://github.com/tsstmldemo/tsstmldemo/blob/main/tml-airflow/logs/logs.txt

TSS Docker Run Command
-----------------------
This is the TML Solution Studio Docker Run command.  Note for MAC users change amd64 to arm64 in the container name. 

.. note::
   docker run -d \-\-net=host \-\-env AIRFLOWPORT=9000  -v <change to your local folder>:/dagslocalbackup:z  -v /var/run/docker.sock:/var/run/docker.sock:z  -v /your_localmachine/foldername:/rawdata:z  \-\-env GITREPOURL=https://github.com/tsstmldemo/tsstmldemo  \-\-env CHIP=amd64 \-\-env TSS=1 \-\-env SOLUTIONNAME=TSS  \-\-env EXTERNALPORT=39399  \-\-env VIPERVIZPORT=49689  \-\-env GITUSERNAME='tsstmldemo'  \-\-env DOCKERUSERNAME=''  \-\-env MQTTUSERNAME=''  \-\-env KAFKACLOUDUSERNAME='<Enter API key>'  \-\-env KAFKACLOUDPASSWORD='<Enter your API secret>'  \-\-env READTHEDOCS='<Enter your readthedocs token>'  \-\-env GITPASSWORD='<Enter personal access token>'  \-\-env DOCKERPASSWORD='<Enter your docker hub password>'  \-\-env MQTTPASSWORD='<Enter your mqtt password>'  \-\-env UPDATE=1  maadsdocker/tml-solution-studio-with-airflow-amd64

TSS Docker Run Command: Parameter Explanation
^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **Parameter**
     - **Explanation**
   * - docker
     - This calls the docker engine
   * - -d
     - This runs your container in **detached** mode
   * - \-\-net=host
     - This give your container access to your host operating system
   * - -v
     - This stands for **volume mapping**.  It maps a local folder

       in your host machine to the folder in the container.  The value **z**

        means the container has **shared access** to your local folder.

        For example, -v /mylocal/folder:/dagslocalbackup:z, means map 

        /mylocal/folder (on my host machine) to **/dagslocalbackup**

        in the contaner.   This allows files generated in the container 

        to be automatically written to your local folder.

   * - \-\-env GITREPOURL
     - This is your Github repo, that you cloned from **https://github.com/smaurice101/raspberrypi**
   * -  \-\-env CHIP=AMD64
     - This is the chip if your are running the TSS on windows/linux.

       If you are running MAC, use **CHIP=ARM64**
   * - \-\-env TSS=1
     - This is the TSS value and MUST be 1.
   * - \-\-env AIRFLOWPORT=9000
     - This is the airflow port for TSS.  Connect to TSS from your browser:

       http://localhost:9000
   * - \-\-env SOLUTIONNAME=TSS
     - This is the solution name.
   * - \-\-env VIPERVIZPORT=49689
     - This is the port the Viperviz binary will listen on for connections.

       Note: If VIPERVIZPORT=-1, a random free port is selected by TSS.
   * - \-\-env EXTERNALPORT=39399
     - This is the external port that will be assigned to your TSS solution for external access.

       You will need this port in the `REST <https://tml.readthedocs.io/en/latest/tmlbuilds.html#step-3b-i-rest-api-client>`_, and `gRPC 
       <https://tml.readthedocs.io/en/latest/tmlbuilds.html#step-3c-i-grpc-api-client>`_ clients.

       Note: if EXTERNALPORT=-1, TSS will choose a free port randomly.

       This external port is used by `Viper binary <https://tml.readthedocs.io/en/latest/usage.html>`_: Viper will be listening on this port 

       for a connection as shown here: :ref:`Your Solution TML Binaries`

       In the TMUX window **Viper-produce**: :ref:`Your Solution TMUX Windows`
   * - \-\-env READTHEDOCS
     - This is the readthedocs API token you created.

       Refer to: `Set up readthedocs <https://tml.readthedocs.io/en/latest/readthedocs.html>`_
   * - \-\-env  GITUSERNAME
     - This is your Githib username.
   * - \-\-env GITPASSWORD
     - This is the Github Personal Access Token you created.

       Refer to: `Creating Github Token: <https://tml.readthedocs.io/en/latest/gitsetup.html>`_
   * - \-\-env DOCKERUSERNAME
     - This is your `Docker Hub <https://hub.docker.com/>`_ username.
   * - \-\-env DOCKERPASSWORD
     - This is your Docker Hub password.
   * - \-\-env MQTTUSERNAME
     - This is your MQTT username. See `Set up HiveMQ <https://tml.readthedocs.io/en/latest/hive.html>`_
   * - \-\-env MQTTPASSWORD
     - This is your MQTT password.
   * - \-\-env KAFKACLOUDUSERNAME
     - This is your API key from Confluent Cloud
   * - \-\-env KAFKACLOUDPASSWORD
     - This is your API Secret from Confluent Cloud.
   * - maadsdocker/tml-solution-studio-with-airflow-amd64
     - This is the TSS container name for AMD64

       If using MAC/Unix use: maadsdocker/tml-solution-studio-with-airflow-arm64

TSS Dashboard URL
-----------------------
This is the visualization URL for your TSS dashboard. Note ports may change at runtime.  The solution documentation will update automatically.

.. important::
   http://localhost:49689/dashboard-rtms-ai-mitre.html?topic=rtms-pgpt-ai-mitre&offset=-1&groupid=&rollbackoffset=400&topictype=prediction&append=0&secure=1

TSS Airflow Port
--------------------------

This is the airflow port in your TSS solution container.  

It can be accessed by entering: http://localhost:9000

TSS Log File Dashboard
-----------------------
This is the log file dashboard for your development TML solution running in TSS.

.. important::
   http://localhost:49689/viperlogs.html?topic=viperlogs&append=0

.. note::
   It should be noted that your solution is running in the TSS Development Environment. This gives TML developers a very good way to test their TML solutions 
   before deploying it.

   The solution ports and links below may not work because they will require your to RUN your solution container first.  After, you run your solution container 
   the links and ports will automatically update in the documentation.

Your Solution Docker Container
--------------------------

.. important::
   Refer to the original solution container and documenation here: https://cybersecurityrtms-3f10-ai.readthedocs.io/en/latest/operating.html

Your Solution Docker Run Command 
-----------------------
This is the Docker Run command for your solution container.  Note ports may change at runtime. The solution documentation will update automatically.

.. code-block::

   docker run -d --net=host -p 5050:5050 -p 4040:4040 -p 6060:6060 \
          --env TSS=0 \
          --env SOLUTIONNAME=cybersecurityrtms-aefa-ai \
          --env SOLUTIONDAG=solution_preprocessing_ai_dag-cybersecurityrtms-aefa \
          --env GITUSERNAME=<Enter Github Username> \
          --env GITPASSWORD='<Enter Github Password>' \          
          --env GITREPOURL=<Enter Github Repo URL> \
          --env SOLUTIONEXTERNALPORT=5050 \
          -v /var/run/docker.sock:/var/run/docker.sock:z \
          -v /your_localmachine/foldername:/rawdata:z \
          --env CHIP=amd64 \
          --env SOLUTIONAIRFLOWPORT=4040 \
          --env SOLUTIONVIPERVIZPORT=6060 \
          --env DOCKERUSERNAME='' \
          --env EXTERNALPORT=39399 \
          --env KAFKABROKERHOST=127.0.0.1:9092 \                    
          --env KAFKACLOUDUSERNAME='<Enter API key>' \
          --env KAFKACLOUDPASSWORD='<Enter API secret>' \          
          --env SASLMECHANISM=PLAIN \                    
          --env VIPERVIZPORT=49689 \
          --env MQTTUSERNAME='' \
          --env MQTTPASSWORD='' \          
          --env AIRFLOWPORT=9000 \
          --env READTHEDOCS='<Enter Readthedocs token>' \
          --env step4cmaxrows="100" \ 
          --env step4crawdatatopic="iot-preprocess" \ 
          --env step4csearchterms="rgx:p([a-z]+)ch ~~~ |authentication failure,--entity-- password failure" \ 
          --env step4crememberpastwindows="500" \ 
          --env step4cpatternwindowthreshold="30" \ 
          --env step4crtmsscorethreshold="0.6" \ 
          --env step4cattackscorethreshold="0.6" \ 
          --env step4cpatternscorethreshold="0.6" \ 
          --env step4crtmsstream="rtms-stream-mylogs" \ 
          --env step4clocalsearchtermfolder="|mysearchfile1,|mysearchfile2" \ 
          --env step4clocalsearchtermfolderinterval="60" \ 
          --env step4crtmsfoldername="rtms2" \ 
          --env step3localfiledocfolder="mylogs,mylogs2" \ 
          --env step4crtmsmaxwindows="1000000" \ 
          --env step9pgptcontainername="maadsdocker/tml-privategpt-with-gpu-nvidia-amd64-v2" \ 
          --env step9contextwindow="8192" \ 
          --env step9vectordimension="768" \ 
          --env step9temperature="0.1" \ 
          --env step4raw_data_topic="iot-raw-data" \ 
          --env step4preprocesstypes="anomprob,trend,avg" \ 
          --env step4jsoncriteria="uid=hostName,filter:allrecords~subtopics=hostName,hostName,hostName~values=inboundpackets,outboundpackets,pingStatus~identifiers=inboundpackets,outboundpackets,pingStatus~datetime=lastUpdated~msgid=~latlong=" \ 
          --env step4preprocess_data_topic="iot-preprocess" \ 
          --env step4ajsoncriteria="uid=tactic,filter:allrecords~subtopics=technique,technique,technique~values=FinalAttackScore,FinalPatternScore,RTMSSCORE~identifiers=FinalAttackScore,FinalPatternScore,RTMSSCORE~datetime=TimeStamp~msgid=Entity,PartitionOffsetFound,NumAttackWindowsFound,NumPatternWindowsFound,SearchEntity,rtmsfolder,CurrentRTMSMAXWINDOW~latlong=" \ 
          --env step4amaxrows="50" \ 
          --env step4apreprocesstypes="avg" \ 
          --env step4araw_data_topic="rtms-pgpt-ai" \ 
          --env step4apreprocess_data_topic="rtms-pgpt-ai-mitre" \  
          /cybersecurityrtms-aefa-ai-amd64

.. tip::
   You can use DEMO credentials for testing and quickly seeing the power of TSS and TML.  

   The demo credentials can be found here: `Demo Credentials <https://tml.readthedocs.io/en/latest/docker.html#tss-demo-github-docker-and-readthedocs-site-credentials>`_

Your Solution Docker Run Command: Parameter Explanation
^^^^^^^^^^^^^^^^^^^^^^

.. important::
   To run this docker container Enter the following CORE parameters: 

      #. KAFKABROKERHOST=127.0.0.1:9092 - this uses the Local Kafka installed in your TML solution container.  
         You can specify a Kafka Cloud URL if using AWS MSK or Confluent Kafka Cloud, simply replace this field.
         
      #. Enter KAFKACLOUDUSERNAME and  KAFKACLOUDPASSWORD IF using Kafka Cloud from AWS MSK and Confluent, if using local kafka (127.0.0.1:9092), these MUST be empty.
      
      #. SASLMECHANISM=PLAIN is set for Local Kafka and Confluent Kafka Cloud.  If using AWS MSK, this MUST be changed to SCRAM512.
      
      #. Enter GITUSERNAME 
      
      #. Enter GITPASSWORD 
      
      #. Enter READTHEDOCS 
      
      #. Update volume mapping: /your_localmachine/foldername:/rawdata:z 
      
      #. IF YOU ARE DISTRUBUTING THIS CONTAINER TO OTHERS THEN SEND THEM THIS DOCKER RUN BUT THEY WILL NEED TO ENTER THE ABOVE CORE PARAMETERS. 
         TO MAKE IT EASY FOR OTHERS TO RUN YOUR SOLUTION YOU CAN USE THE TSSTMLDEMO GITHUB AND READTHEDOCS ACCOUNT - UPDATE THE FOLLOWING: 
      
      #.  GITUSERNAME=tsstmldemo 
      
      #. GITREPOURL=https://github.com/tsstmldemo/tsstmldemo 
      
      #. GITPASSWORD=<Will be retrieved from OS IF using tsstmldemo> 
      
      #. READTHEDOCS=aefa71df39ad764ac2785b3167b77e8c1d7c553a 

      #. step4cmaxrows=100 this means the number of offsets to rollback.  Change to higher or lower number.  Higher number more data will be processed and more memory consumed.

      #. step4crawdatatopic=iot-preprocess, this is the Step 4 preprocessing topic of the entities.  If this is empty string, no entities are cross-refenced with the log files.  Only log files will be processed.

      #. step4csearchterms=rgx:p([a-z]+)ch ~~~ |authentication failure,--entity-- password failure, these are the fixed search terms.  You can specify dynamic search terms in the field step4clocalsearchtermfolder

      #. step4crememberpastwindows=500, this is the past, short-term windows for TML to remember.  TML RTMS will go back 500 sliding time windows.

      #. step4cpatternwindowthreshold=30, this is the maximum pattern threshold before raising an alarm.

      #. step4crtmsscorethreshold=0.6, this is the RTMS score threshold.  This is used to send messages that exceed this RTMS threshold to its own rtms topic.

      #. step4cattackscorethreshold=0.6, this is the Attack score threshold.  This is used to send messages that exceed this attack threshold to its own attack topic.

      #. step4cpatternscorethreshold=0.6, this is the Pattern score threshold.  This is used to send messages that exceed this pattern threshold to its own pattern topic.

      #. step4crtmsstream=rtms-stream-mylogs, this is the kafka topic that stores ALL the results from RTMS.

      #. step4clocalsearchtermfolder=|mysearchfile1,|mysearchfile2, this is name of the folders that contain text files for searches. A | for OR, and @ for AND.  TML will read the search terms in real-time and immediately start applying them to the streamed data.

      #. step4clocalsearchtermfolderinterval=60, this is the number in seconds that the files in the folders specified in step4clocalsearchtermfolder, will be read.  So, 60 means, read files every 60 seconds.

      #. step4crtmsfoldername=rtms2, TML RTMS will output logs of the search results to GitHub.  This is convenient for testing and validation.  NOTE: Only the latest 950 files will be sent to GitHub because GitHub has a maximum file limit of 1000.  

      #. step3localfiledocfolder=mylogs,mylogs2, these are the folders that contain your log text log files.  These are read in STEP 3 LOCALFILE task. 

      #. step4crtmsmaxwindows=1000000, this is the maximum number of windows for LONG-TERM pattern matching.  Here, TML will go-back 1,000,000 sliding time windows, which in effect could be months of analysis.  Yoi can easily increase this number.
      
      - PLEASE NOTE: THE GITHUB AND READTHEDOCS ACCOUNTS ARE PUBLIC AND SHARED ACCOUNTS BY OTHERS.  
      
      - THEY ARE MEANT ONLY FOR QUICK DEMOS.  IDEALLY, PERSONAL GITHUB AND READTHEDOCS ACCONTS SHOULD BE USED.

.. list-table::

   * - **Parameter**
     - **Explanation**
   * - docker
     - This calls the docker engine
   * - -d
     - This runs your container in **detached** mode
   * - \-\-net=host
     - This give your container access to your host operating system
   * - \-\-env TSS=0
     - Internal TSS variable. MUST be 0.
   * - \-\-env SOLUTIONNAME
     - This is the name of your TML solution.
   * - \-\-env SOLUTIONDAG
     - This is the name of the DAG that comprises your solution.

       This DAG is triggered automatically when you run this container.
   * - \-\-env  SOLUTIONVIPERVIZPORT=6060
     - This is the port Viperviz is listening.  

       You point your browser to this port. See :ref:`Your Solution Dashboard URL`
   * - \-\-env CLIENTPORT=Not Applicable
     - Use this port if you are externally connecting to the TML/TSS solution using

       REST API or gRPC clients.  You will need this port in the `REST <https://tml.readthedocs.io/en/latest/tmlbuilds.html#step-3b-i-rest-api-client>`_, and `gRPC <https://tml.readthedocs.io/en/latest/tmlbuilds.html#step-3c-i-grpc-api-client>`_ clients.

       This external port is used by `Viper binary <https://tml.readthedocs.io/en/latest/usage.html>`_: Viper will be listening on this port 

       for a connection as shown here: :ref:`Your Solution TML Binaries`

       In the TMUX window **Viper-produce**: :ref:`Your Solution TMUX Windows` 
   * - \-\-env  VIPERVIZPORT=49689
     - This is the port Viperviz is listening in TSS.  

       You point your browser to this port. See :ref:`Your Solution Dashboard URL`
   * - \-\-env  AIRFLOWPORT=9000
     - This is the port for Airflow in TSS solution studio container.
   * - \-\-env  SOLUTIONAIRFLOWPORT=4040
     - This is the port for Airflow in TML solution container.

       Note: This is provided mainly for debugging and testing purposes only.
   * - \-\-env  GITUSERNAME
     - This is your Github username.
   * - \-\-env GITPASSWORD
     - This is the Github Personal Access Token you created.

       Refer to: `Creating Github Token <https://tml.readthedocs.io/en/latest/docker.html#generating-personal-access-tokens-in-github>`_
   * - \-\-env GITREPOURL
     - This is your Github repo, that you cloned from **https://github.com/smaurice101/raspberrypi**
   * - \-\-env DOCKERUSERNAME
     - This is your Docker username.
   * - \-\-env READTHEDOCS
     - This is the readthedocs API token you created.

       Refer to: `Set up readthedocs <https://tml.readthedocs.io/en/latest/readthedocs.html>`_
   * - \-\-env CHIP=amd64
     - This is the chip family of your OS.
   * - \-\-env EXTERNALPORT=39399
     - This is the external port that you can use when making an external 
    
       connection to your TML solution running in TSS Dev environment.
   * - \-\-env SOLUTIONEXTERNALPORT=5050
     - This is the external port that you can use when making an external connection to your TML solution

       for external data ingestion.  if SOLUTIONEXTERNALPORT=-1, TSS selects a free port randomly.
   * - \-\-env MQTTUSERNAME
     - This is your MQTT username
   * - \-\-env MQTTPASSWORD
     - This is your MQTT password.
   * - \-\-env KAFKACLOUDUSERNAME
     - This is your API key from Confluent Cloud
   * - \-\-env KAFKACLOUDPASSWORD
     - This is your API Secret from Confluent Cloud.
   * - /cybersecurityrtms-aefa-ai-amd64
     - Your solution container name. 

Your Solution Airflow Port
--------------------------

This is the airflow port in your solution container.  

It can be accessed by entering: http://localhost:4040

.. important::
   4040

   Note: This port will change when SOLUTIONAIRFLOWPORT=-1, you can set it to 

   particular number.

Your Solution External Port
-----------------------
This is the Docker Run command for your solution container.  Note ports may change at runtime. The solution documentation will update automatically.

.. important::
   5050

   This is the external port that you can use when making an external connection to your TML solution for external data ingestion.  You will need this port in the `REST <https://tml.readthedocs.io/en/latest/tmlbuilds.html#step-3b-i-rest-api-client>`_, and `gRPC <https://tml.readthedocs.io/en/latest/tmlbuilds.html#step-3c-i-grpc-api-client>`_ clients.

   Note: if SOLUTIONEXTERNALPORT=-1, TSS will choose a free port randomly.

   This external port is used by `Viper binary <https://tml.readthedocs.io/en/latest/usage.html>`_: Viper will be listening on this port 

   for a connection as shown here :ref:`Your Solution TML Binaries`

   In the TMUX window **Viper-produce**: :ref:`Your Solution TMUX Windows` 

Non-Solution vs Solution Ports
^^^^^^^^^^^^^^^^^^^^^^

Non-solution ports are only for TSS, this is because TSS includes a TML Dev environment to allow TML solution developers to test their solutions.

Solution ports are for your TML solution that you created and will deploy.

.. important::
   It is important to note the difference between the following ports:
    - AIRFLOWPORT and SOLUTIONAIRFLOWPORT
    - EXTERNALPORT and SOLUTIONEXTERNALPORT
    - VIPERVIZPORT and SOLUTIONVIPERVIZPORT

    The reason is because TSS includes a Development environment for TML 

    solutions, many times you will want to run your solution in Dev and run

    it in its own solution container for testing before you deploy your

    solution.  But, since ONLY ONE application can listen on a port, 

    we must assign a different port to the solutions so there is no 

    port conflict between applications in DEV and PROD.

    However, if you set all port to -1, TSS will randomly choose

    free ports for you.  The reason for setting the ports with an 

    actual number that is NOT -1, is if you want to scale your TML solution

    with Kubernetes and producing data using REST or gRPC and do not want

    ports to keep changing and breaking your app.

Your Solution Dashboard URL
-----------------------
This is the visualization URL for your TML dashboard. Note ports may change at runtime.  The solution documentation will update automatically.

.. important::
   http://localhost:6060/dashboard-rtms-ai-mitre.html?topic=rtms-pgpt-ai-mitre&offset=-1&groupid=&rollbackoffset=400&topictype=prediction&append=0&secure=1

Your Solution Log File Dashboard
-----------------------
This is the log file dashboard for your TML solution running.

.. important::
   http://localhost:6060/viperlogs.html?topic=viperlogs&append=0

Your Solution Dashboard URL: Parameter Explanation
^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **Parameter**
     - **Explanation**
   * - http://localhost:6060/<html file>
     - This is the URL pointing to an html file running inside your solution container.

       Refer to: `TML Real-time dashboards <https://tml.readthedocs.io/en/latest/dashboards.html>`_
   * - SOLUTIONVIPERVIZPORT=6060
     - This is the port `Viperviz <https://tml.readthedocs.io/en/latest/usage.html>`_ is listening on.
   * - topic
     - This is the topic that the TML binary `Viperviz <https://tml.readthedocs.io/en/latest/usage.html>`_ 

       is reading (consuming) in Apache Kafka and sending it to your broweser over websockets.  
   * - offset
     - This value tells the Viperviz binary to read the latest real-time data. 

       **offset=-1**, means to go to the end of the data stream and get the latest record.
   * - groupid
     - This can be empty. 
   * - rollbackoffset
     - This is the number of offsets to **rollback** the data stream from the **offset** value.

       Note: If you increase this number, Viperviz will send more data to your browser.  

       But be carefull, too much data may crash your browser or computer.
   * - topictype
     - Leave as is.
   * - append
     - This tells your html file whether to append or not the data streaming to your browser.

       If append=0, the html will not apend, if append=1, then data will accumulate in your browser.
   * - secure
     - This tells Viperviz whether to encrypt your data to the browser.  

       If secure=1, data are encrypted, secure=0 no encryption.

[cybersecurityrtms-aefa-ai] Github Repo
---------------
This is the Github repo for all your solution code

.. important::
   https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa-ai

Readthedocs URL
---------------
This is this URL.

.. important::
   https://cybersecurityrtms-aefa-ai.readthedocs.io

Solution Trigger DAG
----------------
This is the name of the solution DAG you chose to trigger.

.. important::
   solution_preprocessing_ai_dag-cybersecurityrtms-aefa

Your Solution TML Binaries 
-----------------------
These are the ports the TML binaries are listening on.

.. important::
   VIPERHOST_PRODUCE=0.0.0.0, VIPERPORT_PRODUCE=5050, VIPERHOST_PREPOCESS=127.0.1.1, VIPERPORT_PREPROCESS=33021, VIPERHOST_PREPOCESS2=127.0.1.1, VIPERPORT_PREPROCESS2=41059, VIPERHOST_PREPOCESS_PGPT=127.0.1.1, VIPERPORT_PREPROCESS_PGPT=39463, VIPERHOST_ML=127.0.1.1, VIPERPORT_ML=34317, VIPERHOST_PREDCT=127.0.1.1, VIPERPORT_PREDICT=43243, HPDEHOST=127.0.1.1, HPDEPORT=37313, HPDEHOST_PREDICT=127.0.1.1, HPDEPORT_PREDICT=39893

Your Solution TMUX Windows 
-----------------------

.. important::
   python-produce-2825-cybersecurityrtms-aefa-ai,solution_preprocessing_ai_dag-cybersecurityrtms-aefa, python-preprocess-7284-cybersecurityrtms-aefa-ai,solution_preprocessing_ai_dag-cybersecurityrtms-aefa, python-preprocess1-4424-cybersecurityrtms-aefa-ai,solution_preprocessing_ai_dag-cybersecurityrtms-aefa, python-preprocess3-378-cybersecurityrtms-aefa-ai,solution_preprocessing_ai_dag-cybersecurityrtms-aefa, python-ai-8234-cybersecurityrtms-aefa-ai,solution_preprocessing_ai_dag-cybersecurityrtms-aefa, viper-produce, viper-preprocess, viper-preprocess-pgpt, viper-ml, viper-predict

- Your solution is running in these  

       TMUX windows:
   
        - To view windows, type:

          **tmux ls**

        - To go inside window, type:

          **tmux a -t <window name>**

        - To exit window, type:

          **CTLR+b, d**

        - To scroll window, type:

          **CTLR+b, [**

        - To un-scroll window, type:

          **CTLR+[**

