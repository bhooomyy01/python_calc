"# python_calc" 
# Python GUI using PyQt

## Install

##### PIP install PyQt5

## Test installation of PyQt5
#### import module
     
import sys  
from PyQt5.QtWidgets import QApplication  
from PyQt5.QtWidgets import QLabel  
from PyQt5.QtWidgets import QWidget  
    
#### Create GUI
app = QApplication(sys.argv)  
window = QWidget()  
window.setWindowTitle('PyQt5 App')  
window.setGeometry(100, 100, 280, 80)  
window.move(600, 15)  
helloMsg = QLabel('This is Test', parent=window)   
helloMsg.move(60, 30)  
window.show()  
    
    
#### Retain GUI Window


sys.exit(app.exec_())
  


# Calculator Using PyQt5 

## View of application
  
      
#### 1. Create view.py
     
#### 2. Import following modules

from PyQt5.QtCore import Qt  
from PyQt5.QtWidgets import QMainWindow      
from PyQt5.QtWidgets import QWidget    
from PyQt5.QtWidgets import QGridLayout    
from PyQt5.QtWidgets import QLineEdit    
from PyQt5.QtWidgets import QPushButton     
from PyQt5.QtWidgets import QVBoxLayout 

    
#### 3. Create GUI class and extend QMainWindow class

class GUI(QMainWindow):

 - ##### Add constructor and Parameter

    - SuperClass Constructor  
    - setWindowTitle  
    - setFixedSize  
    - generalLayout  
    - centralWidget  
    - createDisplayLED  
    - createButtons  

 - ##### Define Methods
   ##### (Which will create method for Display Panel, Buttons layout and method for set/get/clear display)

    - createDisplayLED()  
    - createButtons()  
    - setDisplayText()  
    - getDisplayText()  
    - clearDisplay()  


## Model of application
      
#### 1. Create model.py
     
#### 2. Create function for calculator's operation


ERROR_MSG = 'ERROR'  
def evaluateExpression(expression):  
    try:  
        result = str(eval(expression, {}, {}))  
    except Exception:  
        result = ERROR_MSG  
    return result  



## Controller of application
     
#### 1. Create controller.py
     
#### 2. Import following module


from functools import partial


    
#### 3. Create Controller class

class Controller:
 - ##### Add constructor

    def _init_(self, model, view):  
        self._evaluate = model  
        self._view = view  
        self._connectSignals()  

 - ##### Define Methods
   ##### (Which will create method for CalculateResult Build expression Connect signals and slots.)

    - calculateResult()  
    - buildExpression()  
    - connectSignals()  


## Main Class
     
#### 1. Create main.py
     
#### 2. Import following module

import sys  
from PyQt5.QtWidgets import QApplication    
from view import GUI  
from model import evaluateExpression  
from controller import Controller  
    
#### 3. Create Main Function

def main():  
pycalc = QApplication(sys.argv)  
view = GUI()  
view.show()  
model = evaluateExpression  
Controller(model=model, view=view)  
sys.exit(pycalc.exec_())  
if _name_ == "_main_":  
main()
