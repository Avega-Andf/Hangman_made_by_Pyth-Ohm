# Hangman Game made by pyth - OHM
## Bibliotecas
##### Import random
+ random.choice()
##### Import time
+ time.sleep()
##### Import Os
  ```python
def clear():
  if os.name == "nt":
    os.system("cls")
  else:
    os.system("clear")
   ```

## Funciones

+ def palabras(idioma):

+ def elegirpalabra():
+ def Funcionadivinar(palabra)->list:
+ def inicio(idioma):

+ def interfaz(idioma):   

+ def juegofacil(vidas,idioma):
+ def juegonormal(vidas,idioma): 
+ def juegodificil(vidas,idioma):

+ def dificultad(dif):
    
+ def llamardificultad(dif,vidas):
            
+ def ganar(idioma):
    
+ def perder(vidas,idioma):
  
+ def funcionamineto(adivinar, idioma, vidas):
    
+ def funcionamineto2pj(idioma, vida1, vida2):
  
## Idioma

Para configurar el idioma de nuestro proyecto utilizamos dos de los idiomas mas utilizado en el mundo (Español e Ingles) y <details><summary> lo configuramos de la siguiente manera :</summary><p>

Como una de las primeras lineas de codigo a ejecutar colocamos el siguiente codigo : 
``` python
print("Digite el idioma deseado :\n 1.Español \n 2.English")
    idioma=int(input(""))
```
de esta manera primero le pedimos al usuario que digite la opcion de idioma que desee y la guardamos en una variable de tipo entero, llamada "idioma".

Deacuerdo al dato ingresado por el usuario ( 1 o 2 ) modificamos todas las partes del codigo que incluian texto. Esta modificacion la hicimos por medio del condicional "if", dentro del cual, colocamos la siguiente condicion. 
Sí la variable llamada idioma era igual a 1 entonces el codigo mostraria el texto en Español, y por el contrario, si dicha variable era igual a 2 entoces mostraria el texto en Ingles.

<details><summary> Como ejemplo de lo anterior tenemos la funcion que creamos para la interfaz :</summary><p> 
  
``` python

      def interfaz(idioma):
    if idioma==1:
        print("JUEGO DEL AHORCADO")
        print("Bienvenido al juego, quieres jugar solo o de a dos personas:?")
        print("1.solo\n2. parejas")
        x = int(input(""))
        if x<1 or x>2:
            print("Esta opcion no existe ")
            
        print("Elige la tematica del ahorcado: ")
        print(" 1. frutas \n 2. superheroes \n 3. animales \n 4.paises \n 5. medios de transporte \n 6. Partes del cuerpo ")
        print(" 7. Objetos del hogar \n 8. Prendas de vestir \n 9. Generos Musicales \n 10. Escritores famosos ")
        print(" 11. Equipos de Futbol \n 12. jugadores de furbol \n 13. Cantantes famosos \n 14. Razas de perros")
        print(" 15. Utiles escolares \n 16. Peliculas famosas ")
        y = int(input(""))
        if y<1 or y>16:
            print("Esta opcion no existe ")
        print("Seleccione la dificultad deseada...\n"+" 1.facil \n"+" 2.normal \n"+" 3.dificil ")
        dif=int(input(""))
        if dif<1 or dif>3:
            print("Esta opcion no existe ")
        return x, y, dif
    if idioma==2:
        print("HANGMAN GAME")
        print("Welcome to the game, do you want to play alone or with two players?")
        print("1. alone\n2. couples")
        x = int(input(""))
        if x<1 or x>2:
            print("Esta opcion no existe ")
        print("Choose the theme of Hangman:")
        print(" 1. fruits \n 2. superheroes \n 3. animals \n 4. countrie \n 5. means of transportation \n 6. body parts")
        print(" 7. household objects \n 8. clothing \n 9. music genres \n 10. famous writers")
        print(" 11. soccer teams \n 12. soccer players \n 13. famous singers \n 14. dog breeds")
        print(" 15. school supplies")
        y = int(input(""))
        if y<1 or y>16:
            print("Esta opcion no existe ")
        print("Select the desired difficulty... \n 1.easy\n 2.normal\n 3.difficult")
        dif=int(input(""))
        if dif<1 or dif>3:
            print("Esta opcion no existe ")
        return x, y, dif
```
</p></details></br>
</p></details></br>

Con esto en mente, aplicamos este mismo concepto en las partes del codigo que lo requerian, como: 
El inicio, La interfaz, En cada una de las dificultades y otras partes. 

## Dificultad

Al momento de elegir el método por el cual acoomodariamos la dificultad de juego teniamos 2 opciones: 
la primera, era por la cantidad de letras de las palabras y la segunda opcion, era por la cantidad de vidas que tendria el jugador.
Debido a esta situacion, como el GRUPO que somos, nos decidimos por el segundo metodo.
Una vez decidido el metodo, simplemente nos quedaba decidir la cantidad de vidas que tendria el jugador en cada dificultad, por lo que decidimos las siguientes cantidades:
``` text

  ----------------------------
  | dificultad | cant. Vidas |
  |--------------------------|
  |--------------------------|
  | Facil      |      8      |
  |--------------------------|
  | Normal     |      6      |
  |--------------------------|
  | Dificil    |      4      |
  |--------------------------|   
```

Ya teniendo esto decidido hicimos 2 lineas de codigo pidiendo al jugador que ingrese la dificultad deseada como lo podemos ver a continuacion : 

```python
print("Seleccione la dificultad deseada...\n"+" 1.facil \n"+" 2.normal \n"+" 3.dificil ")
        dif=int(input(""))
```
<details><summary> Nota :</summary><p>  esta parte del codigo se encuentra en la funcion de interfaz que se mostró anteriormente. Ademas de que tambien esta en ingles. 
</p></details></br>

Para implementar esto en el juego, creamos una funcion para cada dificultad. En estas funciones se mostraba al usuario una imagen dependiendo de la cantidad de vidas que le queden al usuario en la partida. 
<details><summary> Esto lo podremos observar en el siguiente codigo (correspondiente a la dificultad dificil) :</summary><p> 
  
```python

def juegodificil(vidas,idioma):
    if idioma == 1:
        mensaje = "tienes "+str(vidas+1)+" vidas"
    if idioma == 2:
        mensaje = "You have "+str(vidas+1)+" lives"

    if vidas == 3:
        vidas3 = [
        "|"+mensaje+"|",    
        "+--+           |",
        "|              |",
        "|              |",
        "|              |",
        "|              |",
        "|              |",
        "================"]
        return vidas3
    elif vidas == 2:
        vidas2 = [
        "|"+mensaje+"|",   
        "+--+           |",
        "|   |          |",
        "|   O          |",
        "|              |",
        "|              |",
        "|              |",
        "================"]
        return vidas2
    elif vidas == 1:
        vidas1 = [
        "|"+mensaje+"|",
        "+---+          |",
        "|   |          |",
        "|   O          |",
        "|  /|\         |",
        "|              |",
        "|              |",
        "================"]
        return vidas1
    elif vidas == 0:
        vidas0 = [
        "|"+mensaje+"|",
        "+---+          |",
        "|   |          |",
        "|   O          |",
        "|  /|\         |",
        "|  / \         |",
        "|              |",
        "================"]
        return vidas0
        
```
Este proceso se hizo tambien para las otras dificultades, pero teniendo en cuenta, que las partes del "ahorcado" que se agregen por cada vida perdida sean proporocionales a las cantidad de vida de cada dificultad.
Tambien se agrego un mensaje que muestre la cantidad de vidas faltantes.

Nota: Estas funciones sirven gracias a un ciclo externo, dicho ciclo hace el proceso de validar las letras y definir las vidas restantes y a su vez cada que hace eso, llama a estas funciones ( dificultad ) para mostrarnos la imagen adecuada a la cantidad de vidas restantes.    

</p></details></br>
