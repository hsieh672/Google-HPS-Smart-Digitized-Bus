# Smart-Digitized-Bus-Google-HPS
Creating a system that enables people with limited mobility to communicate with drivers at bus stop signs.    
## Development Concept
![WHY](https://github.com/hsieh672/Smart-digitized-Bus-Google-HPS/blob/main/imag/WHY.png)
## Architecture
![cponcept](https://github.com/hsieh672/Smart-digitized-Bus-Google-HPS/blob/main/imag/concept.png)  
## Flow
1. Create a cloud server  
   1. [How to build a cloud server](https://www.youtube.com/watch?v=5OL7fu2R4M8&ab_channel=JayMartMedia)  
   2. [Sockets Tutorial with Python 3](https://pythonprogramming.net/sockets-tutorial-python-3/)  
   There are five videos; the first three introduce the usage of sockets, and the current program is essentially modified in the fourth and fifth segments to change from a 1-to-many chat room to 1-to-1 messaging.

2. Execute server.py with an SSH connection on the cloud server.  
3. After confirming that the IP in client.py is the external IP of the cloud server, run client.py and enter the client's name (this step should also be included in the program to define the code for each Raspberry Pi directly, simulating the bus code).  
```sh
    message = input(f'{my_username} > ')
    message = ''
```
4. Ensure that the IP address in main_client.py matches that of the cloud server, and then execute main_client.py (to simulate the sending of bus stop signs).  
5. Enter the name and data of the object to be sent in main_client.py.  
```sh
    target = input('{send to: } > ')
    target = target.encode('utf-8')
    target_header = f"{len(target):<{HEADER_LENGTH}}".encode('utf-8')
    client_socket.send(target_header + target)
    message = input(f'{my_username} > ')
```
## MQTT-The medium of message transmission
![MQTT](https://github.com/hsieh672/Smart-digitized-Bus-Google-HPS/blob/main/imag/MQTT.png)  
## System On the Bus
We must use a Raspberry Pi, a Raspberry Pi NFC reader, and three LEDs on the bus.  
![RFID](https://github.com/hsieh672/Smart-digitized-Bus-Google-HPS/blob/main/imag/RFID.png)  
![LED](https://github.com/hsieh672/Smart-digitized-Bus-Google-HPS/blob/main/imag/LED.png)  
## System on the Bus Stop
We must use a Raspberry Pi, a Raspberry Pi NFC reader, and a Raspberry Pi 7-inch touchscreen display at the bus stop.  
![GUI](https://github.com/hsieh672/Smart-digitized-Bus-Google-HPS/blob/main/imag/GUI.png)
## Materials
1. Raspberry Pi 3 * 2  
2. Raspberry Pi 7 inch touch screen display  
3. Raspberry Pi NFC reader *2  
4. EQMX cloud  
5. LED * 3  
