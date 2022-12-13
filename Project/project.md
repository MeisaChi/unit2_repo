![weather.png](weather_asbt.png)
### Member: Meisa Chi, Daiichiro Nakanishi

# Unit 2: A Distributed Weather Station for ISAK

## Criteria A: Planning

## Problem definition
**Client:** Masamu Oshita (16)
![](masamu.png)

**Context:** The client is a student of UWC ISAK Japan and he is currently suffering from difference in the temperature and humidity insides his room compared to the outer space in the ISAK campus. His room is too hot and dry compared to outside which is too cold and humid. And he want to have a device that would let him measure the temperture and humidity in the room, to compare to the areas outside his room, and see how he can sort out a way to adjust his room's condition to fit with the campus condition.


**Problem:** He has limited budget to buy the device that can measure the temperture and humidity.


## Proposed Solution
Considering the client requirements an adequate solution includes a low cost sensing device for humidity and temperature and a custom data script that process and anaysis the samples acquired. For a low cost sensing device an adequate alternative is the DHT11 sensor[^1] which is offered online for less than 5 USD and provides adequare precision and range for the client requirements (Temperature Range: 0°C to 50°C, Humidity Range: 20% to 90%). Similar devices such as the DHT22, AHT20 or the AM2301B [^2] have higher specifications, however the DHT11 uses a simple serial communication (SPI) rather than more eleborated protocols such as the I2C used by the alternatives. For the range, precision and accuracy required in this applicaiton the DHT11 provides the best compromise. Connecting the DHT11 sensor to a computer requires a device that provides a Serial Port communication. A cheap and often used alternative for prototyping is the Arduino UNO microcontroller [^3]. "Arduino is an open-source electronics platform based on easy-to-use hardware and software"[^4]. In additon to the low cost of the Arduino (< 6USD), this devide is programable and expandable[^1]. Other alternatives include diffeerent versions of the original Arduino but their size and price make them a less adequate solution.

Considering the budgetary constrains of the client and the hardware requirements, the software tool that I proposed for this solution is Python. Python is open source, it is mature and supported in mutiple platforms (platform-independent) including macOS, Windows, Linux and can also be used to program the Arduino microprocessor 56. In comparison to the alternative C or C++, which share similar features, Python is a High level programming language (HLL) with high abstraction 7. For example, memory management is automatic in Python whereas it is responsability of the C/C++ developer to allocate and free up memory 7, this could result in faster applications but also memory problems. In addition a HLL language will allow me and future developers extend the solution or solve issues proptly.


## Design Statement
We will design a system on python where we can record the past 48 hours data on temperature and humidity, and then show the data as a line graph, and also show it as a linear graph. It can also compare indoors and outdoors, see the highest, the lowest and the average for both datas. We will make a poster for the client to show all the data and result that we will get. We will take the data by using Arduino and it's sensor. We will take 1 month to complete all the coding and making poster.


[^1]: Industries, Adafruit. “DHT11 Basic Temperature-Humidity Sensor + Extras.” Adafruit Industries Blog RSS, https://www.adafruit.com/product/386. 
[^2]: Nelson, Carter. “Modern Replacements for DHT11 and dht22 Sensors.” Adafruit Learning System, https://learn.adafruit.com/modern-replacements-for-dht11-dht22-sensors/what-are-better-alternatives.   
[^3]:“How to Connect dht11 Sensor with Arduino Uno.” Arduino Project Hub, https://create.arduino.cc/projecthub/pibots555/how-to-connect-dht11-sensor-with-arduino-uno-f4d239.  
[^4]:Team, The Arduino. “What Is Arduino?: Arduino Documentation.” Arduino Documentation | Arduino Documentation, https://docs.arduino.cc/learn/starting-guide/whats-arduino.  

## Success Criteria

1. The solution provides a visual representation of the Humidity and Temperature values inside a dormitory (Local) and outside the house (Remote) for a period of minimum 48 hours. 
2. The solution provides a mathematical modelling for the Humidity and Temperature levels for each Local and Remote locations. ```(SL: linear model)```
3. The solution provides a comparative analysis for the Humidity and Temperature levels for each Local and Remote locations including mean, standad deviation, minimum, maximum, and median.
4. ```(SL)```The Local samples are stored in a csv file.
5. Create a prediction the subsequent 12 hours for both temperature and humidity.
6. A poster summarizing the visual representations, model and analysis is created and communicated.










# Criteria B: Design

## System Diagram **SL**
![](sysdim_sl.png)

**Fig.1** shows the system diagram for the proposed solution (**SL**). The indoor variables will be measured using an Arduino microprocessor and the sensor DHT11 conencted to the local computer (Laptop) located inside a room. The outdoor variables will be requested to the remote server using a GET request to the API of the server at ```192.168.6.147/readings```. The local values are stored in a CSV database locally.

## Test Plan
| Type | Input | Process | Output |
|---------|----------------------------------|---------------------------------------|-------------|
| Performance testing  | Code to connect with Arudino and get the data. | 1. Run the code. / 2. Wait unitil the responce come | Computer get the data from ardino in 10 seconds. |
| Unit testing  | Code for taking the data from my room|1. Running the code with Python. / 2. Wait for 48 hours to collect the data. / 3. Check whether I could take data or not.|There will be many datas which will be taken once in 5 minutes.|
| Performance testing  | Code to connect with the school server| 1. Run the code. / 2. Wait unitil the responce come | Computer get the data from ardino in 20 seconds.  |
| Unit testing  | Code for taking the data from the server|1. Running the code with Python. / 2. Wait until all the data appears. / 3. delete the data that I don't use for project|There will be many datas which will be taken once in 5 min by server in Asama Lounge. |
| Unit testing  | Code for making a graphs| 1. Running the code with Python. / 2. Wait until all the graphs appears.  | Check whether data comes from CSV files and have a correct plot, correct line and explaination.|

## Record of Tasks
| Task No | Planned Action                                                | Planned Outcome                                                                                                 | Time estimate | Target completion date | Criterion |
|---------|---------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|---------------|------------------------|-----------|
| 1       | Write the Problem context                        |Complete writing the problem context| 10min         | Nov 22                 | A         |
| 2       | Write the Design Statement                        |Complete writing the design statement| 10min         | Nov 29                 | A         |
| 3       | Created program for collecting data                   |   Create a program to collect room data and put them into a csv file   | 3hours         | Dec 2                 | C         |
| 4       | Tested collecting data                     |  A list of datas and some issues to fix | 48hours         | Dec 7,8                 | C         |
| 5       | Collect data                      |576 datas on the csv file  | 48hours         | Dec 10,11                 | C         |
| 6       | Finalizing, fixing data                   |    A completed csv file available to use for graph | 2hours         | Dec 12                 | C         |
| 7       | Creating code for creating graphs and predictions                  |A program that shows the graph for room/campus temp/hum, creates predictions and compares the 2 datas     | 3hours         | Dec 12                 | C         |
| 8       | Work on writing criteria C                  |List the techniques used, explain some parts of the program| 1hour         | Dec 12                 | C         |

## The way we store the data
We stored Campus data and Room data in the different CSV file separately. (Making "room.csv" and "campus.csv") And we were getting the data from these csv files to make a graphs or any other results.
![](csvs.png)

## Flowcharts
### Getting data from the server
```.py
req = requests.get('http://192.168.6.142/readings')
data = req.json()
readings = data["readings"][0]
currentT = ''
currentH = ''
for r in readings:
    if r["sensor_id"] == 4:
        currentH = r['value']
    elif r["sensor_id"] == 5:
        currentT = r['value']

    date = r['datetime']
    date2 = date.replace('T', ' ')
    file = open("campus.csv", "a")
    file.write(f"{currentT}0, {currentH}0, {date2}\n")
    file.close()
```
![](miro.png)
### Smoothing the data
```.py
samples_per_hour = 12
x_per_hour = []
hour = 0

for i in range(0,len(room_temp),samples_per_hour):
    data1 = room_temp[i:i+samples_per_hour]
    room_temp_s.append(sum(data1)/samples_per_hour)
    x_per_hour.append(hour)
    hour += 1
```
![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/Smoothing%20the%20data.jpg)
### Creating the 'x' value 
```.py
x = []
for i in range(0, len(room_temp_s)):
    x.append(i)
```
![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/Creating%20the%20'x'%20value.jpg)







# Criteria C: Development

## Existing tools
|Softwear tools| Coding tools | Libraries |
|-|-|-|
| Python / Pycharm Edu | For loops |time|
|Arudino| While loops |serial|
|| |requests|
|| |csv|
|| |matplotlib|
|| |numpy|
|| |datetime|
|| |numpy|
|| |json|

## List of techniques used
| Collecting data (Room) | Collecting data (Campus) | Lists | Playing with data | Graphing |
|-|-|-|-|-|
| | Reading data from a server | Defining Lists | Setting ranges to actions | Creating a grid |
| | Converting data into readable data (.json) | Adding elements onto Lists (.append) | Find the number of data in a list (len) | Plotting graphs on grid |
| | Creating lists from servers | Dictionaries | Predictions, Linear lines (Numpy) | Plotting lines and errorbars |

## Computational Thinking

### Decomposition
In computational thinking, decomposition is the process of breaking down a problem into a number of smaller problems that can more easily be addressed. So we decompose the part we have to take a data from server to three parts: reading the data from server, removing the complex strings that we didn't need, Adding the data to the CSV files.
```.py
# Reading the data
req = requests.get('http://192.168.6.142/readings')
data = req.json()
readings = data["readings"][0]
currentT = ''
currentH = ''

# Removing the unnecessary strings
for r in readings:
    if r["sensor_id"] == 4:
        currentH = r['value']
    elif r["sensor_id"] == 5:
        currentT = r['value']

# Adding the data on the CSV files
    date = r['datetime']
    date2 = date.replace('T', ' ')
    file = open("campus.csv", "a")
    file.write(f"{currentT}0, {currentH}0, {date2}\n")
    file.close()
```

### Pattern Recognition and Abstraction
In computational thinking, pattern recognition is the process of identifying patterns in a data set to categorize, process and resolve the information more effectively. And abstraction is the process of filtering out – ignoring - the characteristics of patterns that we don't need in order to concentrate on those that we do. So we functioned the code we needed to read the data from Arduino so we didn't have to write it every time. As a result, we felt that our work became more efficient.
```.py
def read():
    data = ""
    while len(data)<1:
        data = arduino.readline()
    return data
```

### Algorithms
In computational thinking, algorithms a plan, a set of step-by-step instructions to resolve a problem. In an algorithm, each instruction is identified and the order in which they should be carried out is planned. So we used the while loop to get the data once in 5 minutes and put it to the CSV file. we can say that this while loop is one of our algorithms that we made for project.
```.py
arduino = serial.Serial(port='/dev/cu.usbserial-110', baudrate=9600, timeout=.1)
def read():
    data = ""
    while len(data)<1:
        data = arduino.readline()
    return data
    
#BELOW is the part that I am explaining as a algorithms

while True:
    time.sleep(300)
    value = read() #wait until data is in the port
    now = datetime.datetime.now()
    msg = value.decode('utf-8').strip()
    msg = msg.replace('Humidity:', '')
    msg = msg.replace('%', '')
    msg = msg.replace('Temperature:', '')
    msg = msg.replace('C', '')


    file = open("room.csv", "a")
    file.write(f"{msg}, {now}\n")
    file.close()
```



## Prototype Codes
These are the codes that we made in python for this project.

**Belows are the codes that takes data**

### Library
This is the library that you can reach out to the data in ardino and read each lines. And you can get all the data from there and use for making graphs, ect.
```.py
arduino = serial.Serial(port='/dev/cu.usbserial-110', baudrate=9600, timeout=.1)
def read():
    data = ""
    while len(data)<1:
        data = arduino.readline()
    return data
```

### Get the data from the school server at Asama Lounge
It is the code that you can get the tempertures and humidities from the server which is located in Asama Lounge. In the first line, it requested to get the data from server with using the extention that requests to get the data from other place. And it read the all the data from server, however, it is still a complex series of strings. So it is getting only temperture and humidity and the exact time that data was taken from all the data with using for loops. After it take temperture, humidity, and time, it records these data on csv file.
```.py
req = requests.get('http://192.168.6.142/readings')
data = req.json()
readings = data["readings"][0]
currentT = ''
currentH = ''
for r in readings:
    if r["sensor_id"] == 4:
        currentH = r['value']
    elif r["sensor_id"] == 5:
        currentT = r['value']

    date = r['datetime']
    date2 = date.replace('T', ' ')
    file = open("campus.csv", "a")
    file.write(f"{currentT}0, {currentH}0, {date2}\n")
    file.close()
```

### Get the data from my room arduino
It is the code that you can get tempertures and humidities of our room from arudino. It is using while roop to get the data once in 5 minutes. If the data were acquired as is, it would be a very complex series of strings.So we have written code to extract only the temperature and humidity from a complex series of strings.Then there is an extension that takes the exact time that data was taken, and the temperature, humidity, and time are all recorded in a CSV file.
```.py
while True:
    time.sleep(300)
    value = read() #wait until data is in the port
    now = datetime.datetime.now()
    msg = value.decode('utf-8').strip()
    msg = msg.replace('Humidity:', '')
    msg = msg.replace('%', '')
    msg = msg.replace('Temperature:', '')
    msg = msg.replace('C', '')


    file = open("room.csv", "a")
    file.write(f"{msg}, {now}\n")
    file.close()
```
**The photo of the place where arduino was put in my room**
![](room.png)

**Belows are the codes that makes graphs and other results**

### Getting the data for making a graph
This is the code that can get the room temperatures, room humidities, campus temperatures, and campus humidities from CSV files.
```.py
with open("room.csv") as room:
    roomdata = room.readlines()
for line in roomdata:
    clear_line = line.strip()
    separated_line = clear_line.split(",")
    room_temp.append(float(separated_line[1]))
    room_hum.append(float(separated_line[0]))

with open("campus.csv") as campus:
    campusdata = campus.readlines()
for line in campusdata:
    clear_line = line.strip()
    separated_line = clear_line.split(",")
    camp_temp.append(float(separated_line[0]))
    camp_hum.append(float(separated_line[1]))
```

### Smoothing the data
This is the code that makes the line smooth when you make a graph. When making a graph, a smooth line is easier to read than a wobbly line, and is considered more suitable for graphing.
```.py
samples_per_hour = 12
x_per_hour = []
hour = 0

for i in range(0,len(room_temp),samples_per_hour):
    data1 = room_temp[i:i+samples_per_hour]
    room_temp_s.append(sum(data1)/samples_per_hour)
    x_per_hour.append(hour)
    hour += 1

for i in range(0,len(room_hum),samples_per_hour):
    data2 = room_hum[i:i+samples_per_hour]
    room_hum_s.append(sum(data2)/samples_per_hour)
    x_per_hour.append(hour)
    hour += 1

for i in range(0,len(camp_temp),samples_per_hour):
    data3 = camp_temp[i:i+samples_per_hour]
    camp_temp_s.append(sum(data3)/samples_per_hour)
    x_per_hour.append(hour)
    hour += 1

for i in range(0,len(camp_hum),samples_per_hour):
    data4 = camp_hum[i:i+samples_per_hour]
    camp_hum_s.append(sum(data4)/samples_per_hour)
    x_per_hour.append(hour)
    hour += 1
```

### Combining data
NEED EXPLAIN
```.py
room_camp_t_mean = []
room_camp_h_mean = []
standard_dev_temp = []
standard_dev_hum = []

for t in range(len(room_temp_s)):
    data_t = [room_temp_s[t], camp_temp_s[t]]
    room_camp_t_mean.append(np.mean(data_t))
    standard_dev_temp.append(np.std(data_t))

for h in range(len(room_hum_s)):
    data_h = [room_hum_s[h], camp_hum_s[h]]
    room_camp_h_mean.append(np.mean(data_h))
    standard_dev_hum.append(np.std(data_h))
```

### Linear Lines
NEED EXPLAIN
```.py
roomt_m, roomt_b = np.polyfit(x, room_temp_s, 1)
print(f"Linear equasion for the room temperature is y={roomt_m:.2f}x+({roomt_b:.2f})")
x_model = [0, len(room_temp_s)]
roomt_model = []
for i in x_model:
    roomt_model.append(roomt_m * i + roomt_b)
roomh_m, roomh_b = np.polyfit(x, room_hum_s, 1)
print(f"Linear equasion for the room humidity is y={roomh_m:.2f}x+({roomh_b:.2f})")
x_model = [0, len(room_hum_s)]
roomh_model = []
for i in x_model:
    roomh_model.append(roomh_m * i + roomh_b)

campt_m, campt_b = np.polyfit(x, camp_temp_s, 1)
print(f"Linear equasion for the campus temperature is y={campt_m:.2f}x+({campt_b:.2f})")
x_model = [0, len(camp_temp_s)]
campt_model = []
for i in x_model:
    campt_model.append(campt_m * i + campt_b)

camph_m, camph_b = np.polyfit(x, camp_hum_s, 1)
print(f"Linear equasion for the campus humidity is y={camph_m:.2f}x+({camph_b:.2f})")
x_model = [0, len(camp_hum_s)]
camph_model = []
for i in x_model:
    camph_model.append(camph_m * i + camph_b)
```
![This is the results](ll.png)

### Graphing Room's data, Campus's data, and Conpeared version.
NEED EXPLAIN
```.py
#grid
fig = plt.figure(figsize=(24,8))
grid = GridSpec(2,8, figure=fig)

#graphing_room
box1 = fig.add_subplot(grid[0, 4])
plt.plot(x, room_temp_s)
plt.plot(x_model, roomt_model, color="red")
plt.title(f"Temperature of room")
x_12 = 60

box2 = fig.add_subplot(grid[1, 3])
plt.plot(x, room_hum_s)
plt.plot(x_model, roomh_model, color="red")
plt.title(f"Humidity of room")
plt.xlabel(f"Hours")
#graphing_campus
box3 = fig.add_subplot(grid[1, 4])
plt.plot(x, camp_temp_s)
plt.plot(x_model, campt_model, color="red")
plt.title(f"Temperature of campus")
plt.xlabel(f"Hours")

box4 = fig.add_subplot(grid[0, 3])
plt.plot(x, camp_hum_s)
plt.plot(x_model, camph_model, color="red")
plt.title(f"Humidity of campus")

#graphing_both
box5 = fig.add_subplot(grid[0:2, 5:8])
plt.errorbar(x, room_camp_t_mean, standard_dev_temp, fmt="o", color="Red")
plt.fill_between(x, room_temp_s, camp_temp_s, alpha=.3, color="red")
plt.title(f"Temperature Compared")
plt.ylabel(f"Temperature (Celcius)")

box6 = fig.add_subplot(grid[0:2, 0:3])
plt.errorbar(x, room_camp_h_mean, standard_dev_hum, fmt="o", color="Red")
plt.fill_between(x, room_hum_s, camp_hum_s, alpha=.3, color="red")
plt.title(f"Humidity Compared")
plt.ylabel(f"Relative Humidity")

plt.show()
```
![This is the results](graphs.png)

### Showing average temperature and humidity, and its prediction.
NEED EXPLAIN
```.py
average_temp_r = sum(room_temp_s)/len(room_temp_s)
print(f"The average temperature in the room in 48 hours is {average_temp_r:.3}")

average_hum_r = sum(room_hum_s)/len(room_hum_s)
print(f"The average humidity in the room in 48 hours is {average_hum_r:.3}")

average_temp_c = sum(camp_temp_s)/len(camp_temp_s)
print(f"The average temperature on campus in 48 hours is {average_temp_c:.3}")

average_hum_c = sum(camp_hum_s)/len(camp_hum_s)
print(f"The average humidity on campus in 48 hours is {average_hum_c:.3}")


room_12_pred_t = roomt_m * x_12 + roomt_b
print(f"The prediction for the room temperature in 12 hours is {room_12_pred_t:.3}")

room_12_pred_t = roomh_m * x_12 + roomh_b
print(f"The prediction for the room humidity in 12 hours is {room_12_pred_t:.3}")
```
![This is the results](ap.png)


# Criteria D: Functionality

A 7 min video demonstrating the proposed solution with narration
