# Тема: 

## Часть 0: настраиваем clipboard sharing в VirtualBox

```
$ sudo apt update
$ sudo apt install virtualbox-guest-x11
$ sudo VBoxClient --clipboard
```
## Часть 1: пробуем запустить нотификацию

```
$ python3
Python 3.8.10 (default, Nov 26 2021, 20:14:08) 
[GCC 9.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import notify2
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ModuleNotFoundError: No module named 'notify2'
>>>
```
```
$ sudo apt install -y python3-pip
```
```
pip3 install notify2
```
```
$ python3
Python 3.8.10 (default, Mar 15 2022, 12:22:08) 
[GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import no
nonlocal   not        
>>> import notify2
>>> notify2.init('Test')
True
>>> notice = notify2.Notification('Hello, world!')
>>> notice.show()
True
>>>
```
![1](https://user-images.githubusercontent.com/39276703/162636017-b4ddc362-7c68-4667-85b8-308fc010bf4c.png)

## Часть 2: Работа через файл

```
$ mkdir notify && cd notify && touch notify.py
$ sudo apt install vim
$ vim notify.py
$ python3 notify.py
```
![2](https://user-images.githubusercontent.com/39276703/162636045-fce141ae-4473-4c0b-94db-edab7159ef0f.png)
![3](https://user-images.githubusercontent.com/39276703/162636046-ce22ffce-5fde-44c7-8304-9bd52742905a.png)


## Часть 3

```python
import notify2
import subprocess

def send_message(header, message):
        notify2.init("Test")
        notice=notify2.Notification(header, message)
        notice.show()

c=subprocess.check_output('/usr/bin/lscpu', shell=True) # Узнаём данные о процессоре
send_message("CPU state", c)
```

![4](https://user-images.githubusercontent.com/39276703/162636081-d123bacd-20d9-4abd-8372-081443f64d5e.png)

#### Так как в данных `/usr/bin/lscpu` нет данных о частоте процессора, то будут использоваться данные об архитектуре Центрального Процессора

```python
import notify2
import subprocess

def send_message(header, message):
        notify2.init("Test")
        notice=notify2.Notification(header, message)
        notice.show()

c = subprocess.check_output('/usr/bin/lscpu', shell=True) # Узнаём данные о процессоре

code = c.decode("utf-8")
data_array = code.split('\n')

for i in data_array:
    mini=i.split(':')
    if mini[0] == 'Architecture':
        architecture = mini[1].strip()


send_message("CPU Architecture", architecture)
```
![5](https://user-images.githubusercontent.com/39276703/162636099-3d8217f1-92ee-4dc4-9761-9c4fee62e07f.png)

## Часть 5: Красивая нотификация

```python
import notify2
import subprocess

def send_message(header, message):
        notify2.init("Test")
        notice=notify2.Notification(header, message)
        notice.show()

c=subprocess.check_output('/usr/bin/lscpu', shell=True) # Узнаём данные о процессоре

code = c.decode("utf-8")
data_array = code.split('\n')

for i in data_array:
    mini=i.split(':')
    if mini[0] == 'Architecture':
        arch = mini[1].strip()

arch = ', '.join(arch.split('_')) + ' бита'

send_message("Архитектура CPU", arch)
```

![VirtualBoxVM_pKexCzNUYq](https://user-images.githubusercontent.com/39276703/162636283-382a236a-1b19-4dbe-a453-af7948765278.png)

## Часть 6: периодическая нотификация

#### Так как нет информации о герцовке процессора было решено просто выводить каждые 30 секунд

#### Вывод аналогичен предыдущей картинке

```python
import notify2
import subprocess
import time
def send_message(header, message):
        notify2.init("Test")
        notice=notify2.Notification(header, message)
        notice.show()

c=subprocess.check_output('/usr/bin/lscpu', shell=True) # Узнаём данные о процессоре

code = c.decode("utf-8")
data_array = code.split('\n')

while (True):
    time.sleep(30)
    for i in data_array:
        mini=i.split(':')
        if mini[0] == 'Architecture':
            arch = mini[1].strip()
            arch = ', '.join(arch.split('_')) + ' бита'
            send_message("Архитектура CPU", arch)
```

## Часть 7: последняя привязка

```
$ sudo apt install screen
$ screen -t Lab1
$ python3 notify.py
```
