# Kafka setup for Occupancy detection

## How to use? 

### Step1 -> Start virtual environment in two terminals

In the 1st terminal Run Zookeeper. Make sure you are inside kafka_2.13-2.5.0.
```
cd kafka_2.13-2.5.0
bin/zookeeper-server-start.sh config/zookeeper.properties
```
In the 2nd terminal Run Kafka server

```
cd kafka_2.13-2.5.0
bin/kafka-server-start.sh config/server.properties
```

I have already created a topic named "VideoStore" in kafka. Open two more tabs of terminal and run the below code to start Virtual environment with the necessary packages. Make sure you are inside the main folders section and not inside kafka_2.13-2.5.0

```
source env/bin/activate
```

Now run the below in one terminal
```
> python producer.py
```
and in another terminal run 
```
> python consumer.py

 * Serving Flask app "consumer" (lazy loading)
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: on
 * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 227-579-036 
```

Now copy the link http://0.0.0.0:5000/video in a browser and you can see the video feed being consumed in the respective port as a consumer. 

# More helpful terminal commands to know

## Start Zoo keeper

Kafka uses ZooKeeper so you need to first start a ZooKeeper server if you don't already have one. You can use the convenience script packaged with kafka to get a quick-and-dirty single-node ZooKeeper instance.

```
> bin/zookeeper-server-start.sh config/zookeeper.properties
```
## Start the Kafka server:

```
> bin/kafka-server-start.sh config/server.properties
```

## Install Kafka for python
```
pip install kafka-python opencv-contrib-python Flask
```

## Start / Make / Deactivate Virtual ENV for python (MAC)

```
python3 -m venv env
source env/bin/activate
deactivate
```

