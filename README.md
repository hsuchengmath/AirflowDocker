# AirflowDocker
Step 1: 建立所需要的資料夾以及設定所需的環境變數

$ mkdir -p ./logs ./plugins ./dags
 
$ echo -e "AIRFLOW_UID=$(id -u)\nAIRFLOW_GID=0" > .env

Step 3: 使用docker compose設定並建置airflow webserver (main => port:8080, flower => port:5555)

$ docker-compose up airflow-init
  
$ docker-compose up -d --build

需要下架Airflow時，執行
$ docker-compose down --volumes --rmi all

**使用docker compose V2時，執行
$ docker compose up airflow-init
  
$ docker compose up -d --build
(將docker-compose 改成docker compose)
