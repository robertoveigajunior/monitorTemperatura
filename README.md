# monitorTemperatura
### O que isso faz?
Mostra em um janela a temperatura do processador do raspberry PI 3

### Linguagem
Python

### Instalando
Primeiro passo é criar o arquivo .py para ler a temperatura real do processador:

```
from Tkinter import *
from subprocess import check_output
import time

root = Tk()
root.title("log")
root.attributes("-topmost", True)
var = StringVar()


temp = check_output(["vcgencmd", "measure_temp"])
var.set(temp)

w = Label(root, width = 25, textvariable = var)
w.pack()

while True:
    time.sleep(2)
    temp = check_output(["vcgencmd", "measure_temp"])
    var.set(temp)
    root.update_idletasks()
```
    
## salve este aquivo nome-arquivo.py

### Por fim digite o comando no terminal
```
sudo nano autostart
```
Dentro do arquivo adicione
```
@python nome-arquivo.py
```

# para testar digite no terminal
```
python nome-arquivo.py

