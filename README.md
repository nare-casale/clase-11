# clase-11
*clases - objetos - atributos y metodos*

**definicion vieja**

nombre_auto = "toyota"
color = "negro"
velocidad_actual = 0

def acelerar (vel):
  return vel + 50

def frenar(vel):
  return vel - 50

**definicion actual**

class auto:
  def __init_ (self,nombre,color):
      self.nombre = nombre
      self.color = color
      self.velocidad = 0

  def acelerar (self):
   self.velocidad += 50

#definir la clase
class Perro:
  def __init__ (self, nombre, raza, edad):
    #2_ caracteristicas
    self.nombre = nombre
    self.raza = raza
    self.edad = edad

 #3_metodos: QUE PUEDE HACER EL PERRO

  def ladrar(self):
     return f"{self.nombre} dice: ¡guau guau!"

  def cumpleaños(self):
    self.edad += 1
    return f"{self.nombre} ahora tiene {self.edad} años"

  def presentarse(self):
    return f"Soy {self.nombre}, soy {self.raza} y tengo {self.edad} años."

# ===== PASO 2: CREAR OBJETOS ====

Perro1 = Perro("max","labrador",3)

Perro2 = Perro("luna","gran danes",2)

# ==== PASO 3: ACCEDER A ATRIBUTOS ====

print(f"nombre del primer perro: {Perro1.nombre}")
print(f"raza del segundo perro: {Perro2.raza}")

# === PASO 4: EJECUTAR METODOS ====

print(Perro1.ladrar())
print(Perro2.presentarse())

# === PASO 5 MODIFICAR ATRIBUTOS ====

Perro1.cumpleaños
print(Perro1.presentarse())


class jugador:
  """
  representa un jugador en un rpg
  tiene estadisticas que evolucionan con sus acciones
  """

  def __init_(self,nombre,clase):
     #ATRIBUTOS BASICOS
     self.nombre = nombre
     self.clase = clase

     #ESTADISTICAS DEL JUGADOR
     self.nivel = 1
     self.experiencia = 0
     self.experiencia_para_subir = 100

     #SALUD Y MANA
     self.vida_maxima = 100
     self.vida_actual = 100
     self.mana_maximo = 50
     self.mana_actual = 50

     #COMBATE
     self.ataque = 15
     self.defemsa = 5
     self.velocidad = 10

     #INVENTARIO (LISTA DE ITEMS)
     self.inventario = []
     self.oro = 0

     #MENSAJE DE BIENVENIDA
     print(f"¡{self.nombre} has entrado al juego como {self.clase}!")

def ganar_experiencia(self,cantidad):
    """gana XP y verifica si sube de nivel"""
    self.experiencia += cantidad
    print(f"{self.nombre} gano {cantidad} XP")

    if self.experiencia >= self.experiencia_para_subir:
        self.subir_nivel

def subir_nivel(self):
    """ sube de nivel y mejora estadisticas """
    self.nivel += 1

    #RECALCULAR XP NECESARIA
    self.experiencia -= self.experiencia_para_subir
    self.experiencia_para_subir = int(self.experiencia_para_subir)

    #MEJORAS DE STATS
    self.vida_maxima += 20
    self.vida_actual = self.vida_maxima
    self.mana_maximo += 10
    self.mana_actual = self.mana_maximo
    self.ataque +=5
    self.defensa +=2

    print(f"¡{self.nombre} SUBIO A NIVEL {self.nivel}!")
    print(f"vida: +20 (ahora{self.vida_maxima})")
    print(f"ataque: +5 (ahora{self.ataque})")

def atacar(self,enemigo_nombre):
    """ realizar un ataque y gasta mana """
    costo_mana = 10

    if self.mana_actual < costo_mana:
        print(f"{self.nombre} no tiene suficiente mana para ganar")
        return False

    self.mana_actual -= costo_mana
    daño = self.ataque +5 #DAÑO BASE + BONIFICACION

    print(f"{self.nombre} ataca a {enemigo_nombre}")
    print(f"daño: {daño}")
    print(f"mana restante: {self.mana_actual}/{self.mana_maximo}")
    return daño

def recibir_daño(self,cantidad):
    """ recibe daño considerando defensa """

    daño_final = max (cantidad-self.defensa)
    self.vida_actual -= daño_final

    print(f"{self.nombre} recibio {daño_final} de daño (defensa aplicada {self.defensa})")

    if self.vida_actual <= 0:
        self.vida_actual = 0
        print(f"¡{self.nombre} ha muerto !")
        return False

    print(f"vida {self.vida_actual}/{self.vida_maxima}")
    return True

def descansar(self):
    """recupera toda la vida y mana """
    self.vida_actual = self.vida_maxima
    self.mana_actual = self.mana_maximo
    print(f"{self.nombre} descanso y se recupero completamente")

def obtener_item(self,item):
    """ agrega un item al inventario """
    self.inventario.append(item)
    print(f"{self.noombre} obtuvo: {item}")

def obtener_oro(self,cantidad):
    """ gana oro """
    self.oro += cantidad
    print(f"{self.nombre} obtuvo {cantidad} de oro (total: {self.oro})")

def mostrar_stats(self):
    """ muestra todas las estadisticas del jugador """
    print(f"\n{'='*50}")
    print(f"ESTADISTICAS DE {self.nombre_upper}")
    print(f"\n{'='*50}")
    print(f"clase:{self.clase}")
    print(f"nivel:{self.nivel}")
    print(f"experiencia:{self.experiencia}/{self.experiencia_para_subir}")
    print(f"vida:{self.vida_actual}/{self.vida_maxima}")
    print(f"mana:{self.mana_actual}/{self.mana_maximo}")
    print(f"ataque:{self.ataque}")
    print(f"defensa:{self.defensa}")
    print(f"oro:{self.oro}")
    print(f"inventario:{self.inventario if self.inventario else 'vacio'}")
    print(f"\n{'='*50}")

def resumen(self):
    """ resumen rapido del juego """
    return (f"{self.nombre} {self.nombre}{self.clase} - {self.vida_actual}/{self.vida_maxima}")
