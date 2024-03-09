# PIAPROGRA
Repositorio para el PIA de prograavanzada
#A)Genere una clase en Python llamada TDevice (Dispositivo Electrónico) con los atributos 
  #de tamaño, peso, altura, marca y comportamiento encender, apagar. 
class TDEVICE:
  Tamaño = 0
  Altura = 0 
  Peso = 0
  Marca = "."
  
  def __init__(self, Tamaño, Altura, Peso, Marca):
   self.Tamaño = Tamaño
   self.Altura = Altura
   self.Peso = Peso
   self.Marca = Marca
   self.Encendido = True
  
  def encender(self):
    if self.encendido:
        print(f"{self.marca} encendido")
    else:
        print(f"{self.marca} ya esta encendido")
  
  def apagar(self):
    if not self.encendido:
        print(f"{self.marca}apagado")
    else:
        print (f"{self.marca} ya esta apagado")


#B) Genere 3 clases que desciendan de TDevice, por ejemplo una TV, Una Licuadora y Un 
#Celular. Agregarle 3 métodos a cada nueva clase, es decir un comportamiento 
#específico para cada nueva clase

class Calculadora (TDEVICE):  #1era clase, calculadora para sumar dos numeros
 def __init__(self, Tamaño, Altura, Peso, Marca, num1, num2):
    super().__init__(Tamaño, Altura, Peso, Marca,)
    self.num1 = num1
    self.num2 = num2
 def sumar(self, num1, num2):
        resultado = num1 + num2
        print(f"el resultado es {resultado}")  
 
class Control_luces(TDEVICE): #2da clase, control remoto para cambiar un foco de luz blanca a luz calida
 luzb = "luz_blanca"
 def __init__(self, Tamaño, Altura, Peso, Marca, luzb):
  super().__init__(Tamaño, Altura, Peso, Marca,)
  self.luzb = luzb
 
 def cambiar_luz(self):
  if self.luzb == "luz_blanca":
     self.luzb = "luz_calida"
  else:
     self.luzb = "luz_blanca"


class lavadora(TDEVICE):#3era clase, lavadora con tres ciclos, llenado, enjuagado y exprimido
 def __init__(self, tamaño, altura, peso, marca):
   super().__init__(tamaño, altura, peso, marca)
   self.llenado = False
   self.enjuagado = False
   self.exprimido = False
 
 def iniciar_llenado(self):
    print("Iniciando el ciclo de llenado...")
    self.llenado = True
 
 def iniciar_enjuagado(self):
     print("Iniciando el ciclo de enjuagado...")
     self.enjuagado = True
 
 def iniciar_exprimido(self):
     print("Iniciando el ciclo de exprimido...")
     self.exprimido = True


#c) Genere 2 instancias de cada una de las clases del punto 17 con diferentes valores en 
#cada uno de los atributos y diferente comportamiento

#instancias de calculadora
calculadora1 = Calculadora(Tamaño=10, Altura=5, Peso=2, Marca="Casio", num1=5, num2=7)
calculadora2 = Calculadora(Tamaño=8, Altura=4, Peso=1.5, Marca="HP", num1=10, num2=3)

# instancias de control_luces
control_luces1 = Control_luces(Tamaño=5, Altura=3, Peso=0.5, Marca="Philips", luzb="luz_blanca")
control_luces2 = Control_luces(Tamaño=4, Altura=2, Peso=0.4, Marca="Sony", luzb="luz_calida")

# instancias de lavadora
lavadora1 = lavadora(tamaño=50, altura=80, peso=30, marca="Samsung")
lavadora2 = lavadora(tamaño=45, altura=75, peso=28, marca="LG")



#d) Genere una clase llamada TPersona con 5 atributos y 5 funciones.  
class TPersona:
 nombre = "."
 apellidop = "."
 apellidom = "."
 edad = 0
 genero = "."

 def __init__(self, tnombre, tapellidop, taltura, tedad, tpeso):
   self.tnombre = tnombre
   self.tapellidop = tapellidop
   self.taltura = taltura
   self.tedad = tedad
   self.tpeso = tpeso
  
 def presentarse(self, tnombre, tapellidop): #funcion 1
   print (f"Hola mi nombre es {tnombre} {tapellidop}")

 def año_de_nacimiento(self,tedad): #funcion 2
   añon = tedad - 2023
   print (f"mi año de nacimiento es {añon}")

 def calcular_imc(self, tpeso, taltura): #funcion 3
   imc = tpeso / ((taltura / 100) ** 2)
   print (f"el imc de esta persona es de {imc}")

 def mayoria_de_edad(self, tnombre, tedad): #funcion 4
   if tedad > 18:
    print(f"{tnombre}, es mayor de edad")
   else:
    print(f"{tnombre}, no es mayor de edad")
   
 def etapa_persona(self, tnombre, tedad): #funcion 5
   if tedad <= 5:
    print (f"{tnombre}, esta en la infancia")
   elif 6 <= tedad <= 5:
    print (f"{tnombre}, esta en la niñez")   
   elif 13 <= tedad <= 18:
    print (f"{tnombre}, esta en la aldolescencia")
   elif 19 <= tedad <= 64:
    print(f"{tnombre}, esta en la adultez")
   else:
     print(f"{tnombre}, esta en la vejez")


#e) Genere 3 clases que desciendan de TPersona, (Por ejemplo un policía, un administrador 
#y un bombero).
     
class Policia(TPersona):
 def __init__(self, tnombre, tapellidop, taltura, tedad, tpeso, numplaca):
   super().__init__(self, tnombre, tapellidop, taltura, tedad, tpeso)
   self.numplaca = numplaca
    

class Administrador(TPersona):
 def __init__(self, tnombre, tapellidop, taltura, tedad, tpeso, id_empleado):
   super().__init__(self, tnombre, tapellidop, taltura, tedad, tpeso)
   self.id_empleado = id_empleado

class Bombero(TPersona):
  def __init__(self, tnombre, tapellidop, taltura, tedad, tpeso, clave):
   super().__init__(self, tnombre, tapellidop, taltura, tedad, tpeso)
   self.clave = clave
  


     
#f) Genere 1 clase que descienda de TPolicia, TAdministrador y TBombero
class cadete(Policia):
 def __init__(self, tnombre, tapellidop, taltura, tedad, tpeso, curso):
   super().__init__(self, tnombre, tapellidop, taltura, tedad, tpeso)
   self.curso = curso
    
class pasante(Administrador):
 def __init__(self, tnombre, tapellidop, taltura, tedad, tpeso, matricula):
   super().__init__(self, tnombre, tapellidop, taltura, tedad, tpeso)
   self.matricula = matricula

class ayudante(Bombero):
  def __init__(self, tnombre, tapellidop, taltura, tedad, tpeso, apodo):
   super().__init__(self, tnombre, tapellidop, taltura, tedad, tpeso)
   self.apodo = apodo


#g) Instanciar 2 veces cada una de las clases del punto 21.

#instancias de cadete
cadete1 = cadete(tnombre="Juan", tapellidop="Pérez", taltura=180, tedad=25, tpeso=70, curso="Curso1")
cadete2 = cadete(tnombre="María", tapellidop="Gómez", taltura=175, tedad=23, tpeso=68, curso="Curso2")

# Instancias de pasante
pasante1 = pasante(tnombre="Carlos", tapellidop="Rodríguez", taltura=170, tedad=22, tpeso=65, matricula="1819209")
pasante2 = pasante(tnombre="Laura", tapellidop="Fernández", taltura=165, tedad=24, tpeso=62, matricula="1514789")

# Instancias de ayudante
ayudante1 = ayudante(tnombre="David", tapellidop="García", taltura=185, tedad=26, tpeso=75, apodo= "garfio")
ayudante2 = ayudante(tnombre="Ana", tapellidop="Martínez", taltura=160, tedad=28, tpeso=68, apodo= "bala")



# H)Define una clase llamada Persona que tenga los siguientes atributos: nombre, edad y 
#genero. Además, la clase debe tener un método llamado presentarse que imprima un 
#mensaje con el nombre y la edad de la persona}
class persona:
 nombre = "."
 edad = 0
 genero = "."
      
 def __init__(self, nombre, edad, genero):
  self.nombre = nombre
  self.edad = edad
  self.genero = genero
      
 def presentarse(self):
  print(f"Hola, soy {self.nombre}, tengo {self.edad} años y mi genero es {self.genero}.")


#I)Crea una subclase llamada Estudiante que herede de la clase Persona y tenga un 
#atributo adicional llamado curso. Además, añade un método llamado estudiar que 
#imprima un mensaje indicando el curso que está estudiando

class estudiante(persona):
 def __init__(self,nombre, edad, genero, curso):
  super().__init__(nombre, edad,genero,)
  self.curso = curso
 
 def estudiar(self,nombre, curso):
   print(f"hola mi nombre es{nombre} y estoy en el curso de {curso} ")




#J)Define una clase llamada Rectángulo que tenga dos atributos: largo y ancho. Además, 
#añade un método llamado área que calcule y devuelva el área del rectángulo.
 class rectangulo:
  base = 0
  altura = 0
 
 def __init__(self, base, altura):
  self.base = base
  self.altura = altura
 
 def calcular(self, base,altura):
  resultado = base * altura
  print (f"El resultado es{resultado}")
