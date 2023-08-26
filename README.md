# Smart-Digitized-Bus-Google-HPS
A system that allows people with limited mobility to communicate with drivers at bus stop signs.
## Development Concept
![WHY](https://github.com/hsieh672/Smart-digitized-Bus-Google-HPS/blob/main/imag/WHY.png)
## Architecture
![cponcept](https://github.com/hsieh672/Smart-digitized-Bus-Google-HPS/blob/main/imag/concept.png)  
## Flow
1. Create a cloud server  
   1. [How to build a cloud server](https://www.youtube.com/watch?v=5OL7fu2R4M8&ab_channel=JayMartMedia)  
   2. [Sockets Tutorial with Python 3](https://pythonprogramming.net/sockets-tutorial-python-3/)  
   There are 5 videos in total, the first three introduce the usage of sockets, and the current program is basically modified with the fourth and fifth segments to    change from a 1-to-many chat room to a 1-to-1 messaging.
3. Run server.py with ssh connection in the cloud server  
4. After confirming that the ip of clinet.py is the external ip of the cloud server, run client.py and fill in the client name (this step should also be written in the program to directly define the code of each Raspberry pi, simulating the bus code)  
```sh
    message = input(f'{my_username} > ')
    message = ''
```
4. Make sure the ip of main_client.py is the same as that of the cloud server, then run main_client.py (to simulate the sending of bus stop signs)  
5. Enter the name and data of the object to be sent in main_client.py  
```sh
    target = input('{send to: } > ')
    target = target.encode('utf-8')
    target_header = f"{len(target):<{HEADER_LENGTH}}".encode('utf-8')
    client_socket.send(target_header + target)
    message = input(f'{my_username} > ')
```
## MQTT-The medium of messages transmission
![MQTT](https://github.com/hsieh672/Smart-digitized-Bus-Google-HPS/blob/main/imag/MQTT.png)  
## System On the Bus
We need to use a Raspberry pi, Raspberry Pi NFC reader, three LED on the bus  
![RFID](https://github.com/hsieh672/Smart-digitized-Bus-Google-HPS/blob/main/imag/RFID.png)  
![LED](https://github.com/hsieh672/Smart-digitized-Bus-Google-HPS/blob/main/imag/LED.png)  
## System on the Bus Stop
We need to use a Raspberry pi, Raspberry Pi NFC reader, Raspberry Pi 7 inch touch screen display on the bus stop  
![GUI](https://github.com/hsieh672/Smart-digitized-Bus-Google-HPS/blob/main/imag/GUI.png)
## Materials
1. Raspberry pi 3 * 2  
2. Raspberry Pi 7 inch touch screen display  
3. Raspberry Pi NFC reader *2  
4. EQMX cloud  
5. LED * 3  
