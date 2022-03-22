# confluent_local_for_kafka_connect_debezium_postgresql


![image](https://user-images.githubusercontent.com/77326619/159463221-175f5a4e-518f-4152-a54f-eb82b11cbfaf.png)
![image](https://user-images.githubusercontent.com/77326619/159463331-90e653da-437e-407a-89fa-a724fd59f563.png)
![image](https://user-images.githubusercontent.com/77326619/159463502-fe26a064-cd25-499b-8104-9f7b06879e6f.png)
$CONFLUENT_HOME/bin/confluent-hub install debezium/debezium-connector-postgresql:latest
pilih 3
![image](https://user-images.githubusercontent.com/77326619/159463687-49a51dca-6ff0-4a36-a488-4a623eeb2c5b.png)
abis itu restart bro
abis itu cek bro
![image](https://user-images.githubusercontent.com/77326619/159464018-a2fbe381-54ed-4d81-a219-654ea2aa8fe5.png)
abis itu lu bikin file debezium.json isi file nya ada diatas ye
abis itu lu run buat daftarin ke connector dan topic

curl -i -X POST -H "Accept:application/json" -H "Content-Type:application/json" 127.0.0.1:8083/connectors/ --data "@debezium.json"

![image](https://user-images.githubusercontent.com/77326619/159464634-691c8d12-e119-4935-96c1-60092143dce3.png)

abis itu lu cek list kafka topic yang ada di kafka lu bro
bin/kafka-topics --bootstrap-server localhost:9092 --list
![image](https://user-images.githubusercontent.com/77326619/159464863-d83c4108-773d-4dd2-b47b-150706dce12e.png)
![image](https://user-images.githubusercontent.com/77326619/159464919-40e2977b-272b-4717-b0ba-cc0cf637ba1d.png)
hasil dari command sebelomnya bakal bikin topic dengan nama postgres.public.ddi

abis itu lu run dah
bin/kafka-console-consumer --bootstrap-server localhost:9092 --topic postgres.public.test
![image](https://user-images.githubusercontent.com/77326619/159465130-ac87f1d7-af7e-4f5e-a33b-1b845e6c7ed8.png)


buat ngetes topic lu konek ga ke debezium sama kafka lu coba lu insert table di postgres lu contoh gue insert table dengan nama pak ipik
![image](https://user-images.githubusercontent.com/77326619/159465557-0b2ccd9a-52b0-4a89-b53d-f999c3da473e.png)



