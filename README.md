# -Raspberry-Pi-connection-to-Google-cloud

                    Google Cloud IoT using Raspberry Pi
Introduction
The Internet of Things (IoT) is a network of physical objects (also known as "things") that are embedded with sensors, software, and other technologies in order to communicate and exchange data with other devices and systems over the Internet. In this code lab, we are going to build a data pipeline that begins with an Internet of Things (IoT) system that collects heart rate data, then uses IoT Core to securely publish the data to a message queue, from which it will be transported to a data warehouse. Although it is helpful to build out the Raspberry Pi, it is not needed for this code lab, and the streaming data can be simulated with a script.

![image](https://user-images.githubusercontent.com/66374184/117496574-3adb8000-af45-11eb-8c7f-9fc264819929.png)

 
After completing the steps in this codelab, we will have a streaming data pipeline feeding a data warehouse from which you can retrieve heart rate data to graph over time.
I.	Hardware Requirements
Raspberry Pi Zero W with power supply, SD memory card and case, USB card reader, USB hub (to allow for connecting a keyboard and mouse into the sole USB port on the Raspberry Pi), GPIO Hammer Headers, Female-to-male breadboard wires, Polar T34 Heart Rate Transmitter and Polar Heart Rate receiver, Soldering iron with solder.
II.	How IoT Core is streamed to Heart Rate Data?
To follow up the steps sign up for the Google Cloud Platform console using your Google account at console.cloud.google.com. By connecting your Raspberry Pi computer to IoT Core, you can stream live heart rate data.
Step 1: Create a new project with name ‘iot-heartrate’. The project ID needs to be a unique name across all Google Cloud projects.
Step 2: In this codelab, we will be using Pub/Sub, Dataflow, Compute Engine and IoT Core, so we'll need to enable those APIs.

![image](https://user-images.githubusercontent.com/66374184/117496608-475fd880-af45-11eb-8409-b838079a988c.png)

 
Step 3:Create a BigQuery table. BigQuery is a serverless, highly scalable, low cost enterprise data warehouse. From the Cloud Console, select BigQuery and then Create new dataset – “heartRateData" 

![image](https://user-images.githubusercontent.com/66374184/117496628-5050aa00-af45-11eb-8b80-c33e26f0a8ff.png)

 
Step 4: Create a Pub/Sub topic and subscription - it is perfect for handling incoming IoT messages and then allowing downstream systems to process them which is why it is tightly linked with Cloud IoT Core.
Step 5:Use a Dataflow Template- A Dataflow template will be used to build a process that monitors a Pub/Sub subject for incoming messages and then transfers them to BigQuery for this lab.

![image](https://user-images.githubusercontent.com/66374184/117496646-56468b00-af45-11eb-81d9-73159b64f9e6.png)


Step 6: Create an IoT Core registry and Add the device to the IoT Core Registry
Step 7: Add the device to the IoT Core Registry and follow further steps.
 
 ![image](https://user-images.githubusercontent.com/66374184/117496662-5d6d9900-af45-11eb-86a3-767b9c6547ae.png)

Step 8: Start the data by using following steps on the terminal/cmd prompt.
 
 ![image](https://user-images.githubusercontent.com/66374184/117496674-6199b680-af45-11eb-9418-d7ab4521881c.png)

Results: We need to check if the data is flowing properly and visualize the data using Google Sheets. 
 
 ![image](https://user-images.githubusercontent.com/66374184/117496698-68282e00-af45-11eb-87d8-a7895e3e84f6.png)

Summary:
This report demonstrates how to use Google Cloud. Using a Google Cloud Dataflow template and Google BigQuery, build a Google Pub/Sub data pipeline with no code. An entire data pipeline, as evidenced by the output above, this is done by using Google IoT Core to secure IoT devices and enable data to flow into Google Pub/Sub, deploying Dataflow from a template and pushing data into BigQuery, and then using the Google Sheets integration to perform a fast data visualization.
