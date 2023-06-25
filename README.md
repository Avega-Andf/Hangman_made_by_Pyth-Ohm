# Hangman Game made by pyth - OHM
## Bibliotecas
##### Import random\
La biblioteca import random nos sirve para importar el módulo random, que nos da funciones para generar números aleatorios y hacer selecciones aleatorias.
Al importar random, se obtiene acceso a funciones como random.random() , random.randint() y random.choice() 
+ random.choice()\
La función random.choice() en Python nos permite elegir de manera aleatoria un elemento de una secuencia, como una lista, una tupla o una cadena de caracteres. En otras palabras, nos brinda la capacidad de seleccionar un elemento al azar de un conjunto de opciones.\
Daurante la elaboracion de juego utilizamos la funcion para escoger una palabra aletoria dentro de la lista llamada "lista" y a esta esta palabra generada darle la variable "y" la cual seria la palabra que el jugador debe adivinar.
 ```python 
palabra = (random.choice(lista[y])).upper() 
   ```
##### Import time\
La biblioteca time nos permite manipular y controlar el tiempo en un programa.
Ofrece funciones para agregar retardos con time.sleep(), obtener la hora actual con time.time(), obtener la hora local con time.localtime(), y formatear la hora y fecha con time.strftime().
+ time.sleep() \
La función time.sleep() nos permite hacer una pausa en la ejecución de un programa durante un tiempo determinado.Duranre el codigo la utilizamos para distaciar temporalmente las "imagenes " del ahorcado.
```python

 ```
##### Import Os
La biblioteca ´os´  nos permite interactuar con el sistema operativo en el que se ejecuta el programa.
Proporciona funciones para manipular archivos y directorios, acceder a variables de entorno del sistema, ejecutar comandos del sistema, manipular rutas de archivos y obtener información del sistema operativo.
Usamos las siguientes  funciones:
  ```python
def clear():#
  if os.name == "nt": #para verificar si el sistema operativo en el que se está ejecutando el programa es Windows. La variable os.name almacena el nombre del sistema operativo.
    os.system("cls")#Este comando  se encarga de limpiar la pantalla de la terminal.
  else: # en casi de que el sistema operativo no sea windows se utiliza la siguiente funcion
    os.system("clear")#Este comando  se encarga de limpiar la pantalla de la terminal en caso de que no sea windows.
   ```

## Funciones

+ def palabras(idioma):
<details><summary> Funcion :</summary><p> 
  
``` python
def palabras(idioma):
    if idioma==1: 
        lista = {
        1 : #Frutas
            ["arandano", "frambuesa", "fresa", "grosella", "limon", "mandarina", "naranja", "pomelo", "aguacate", "carambola", "chirimoya", "coco", "datil", "kiwi", "mango", "papaya", "pina", "platano", "cereza", "ciruela", "kaki", "manzana", "melocoton", "nispero", "pera", "uva", "almendra", "avellana", "cacahuete", "castana", "nuez"],

        2 : #Superheroes
            ["antman", "aquaman", "atom", "batgirl", "batman", "blackpanther", "blackwidow", "blade", "bluebeetle", "booster", "cable", "captainamerica", "captainmarvel", "catwoman", "colossus", "cyclops", "daredevil", "deadpool", "doctorfate", "doctorstrange", "elektra", "falcon", "firestorm", "flash", "gambit", "ghostrider", "greenarrow", "greenlantern", "groot", "hawkeye", "hellboy", "hulk", "humantorch", "huntress", "iceman", "invisiblewoman", "ironfist", "ironman", "jeangrey", "joker", "jubilee", "juggernaut", "kittypryde", "loki", "lukecage", "magneto", "martianmanhunter", "misterfantastic", "moonknight", "msmarvel", "mystique", "namorita", "nightcrawler", "nightwing", "nova", "omegared", "phoenix", "plasticman", "poisonivy", "powergirl", "professorxavier", "psylocke", "punisher", "quicksilver", "raven", "redhood", "robin", "rocketeer", "rogue", "sabretooth", "scarletwitch", "shadowcat", "shazam", "shehulk", "silversurfer", "spiderman", "starfire", "storm", "submariner", "supergirl", "superman", "swampthing", "thing", "thor", "tigra", "venom", "vision", "warmachine", "wasp", "watchmen", "wolverine", "wonderwoman", "zatanna"] ,      

        3 : #animales
            ["perro", "gato", "elefante", "jirafa", "leon", "tigre", "lobo", "oso", "cebra", "hipopotamo", "rinoceronte", "vaca", "oveja", "cerdo", "conejo", "raton", "ardilla", "pato", "pavo", "gallina", "gallo", "pajaro", "loro", "pinguino", "tortuga", "cocodrilo", "serpiente", "lagarto", "camaleon", "rana", "sapo", "tiburon", "ballena", "delfin", "pez", "caballo", "burro", "cebra", "avestruz", "canguro", "koala", "panda", "camello", "hormiga", "abeja", "araña", "escarabajo", "mariposa", "mosquito"],

        4 : # Paises
            ["argentina", "australia", "brasil", "canada", "china", "colombia", "egipto", "espana", "estados unidos", "francia", "india", "inglaterra", "italia", "japon", "mexico", "peru", "rusia", "sudafrica", "suiza", "tailandia", "turquia", "uruguay", "venezuela", "alemania", "arabia saudita", "belgica", "chile", "dinamarca", "ecuador", "filipinas", "grecia", "holanda", "indonesia", "irlanda", "israel", "kenia", "malasia", "noruega", "nueva zelanda", "panama", "polonia", "portugal", "republica checa", "singapur", "suecia", "vietnam", "cuba", "costa rica", "honduras", "nicaragua"],
            
        5 : # Medios de transporte
            ["automovil", "camion", "motocicleta", "bicicleta", "autobus", "triciclo", "carroza", "furgoneta", "remolque", "tren", "tranvia", "barco", "yate", "avion", "helicoptero", "coche de carreras", "camioneta", "caravana", "patineta", "grua", "excavadora", "ambulancia", "motonieve", "carretilla", "carro de golf", "tractor", "segway", "carro de bomberos", "trineo", "hidroavion", "carro de caballos", "tanque", "submarino", "quad", "carro blindado", "trailer", "monopatin", "aerodeslizador", "tuktuk", "carro de combate", "grua movil", "autobus escolar", "moto de agua", "globo aerostatico", "trolley", "mototaxi", "carro de helados", "autogiro", "carro de reparto", "tren de alta velocidad"],

        6 : # Partes del cuerpo
            ["cabeza", "cuello", "hombro", "brazo", "codo", "muneca", "mano", "dedo", "una", "pecho", "espalda", "estomago", "cintura", "cadera", "pierna", "rodilla", "tobillo", "pie", "talon", "dedo del pie", "una del pie", "ojo", "ceja", "parpado", "nariz", "oreja", "labio", "diente", "barbilla", "mejilla", "lengua", "mandibula", "cerebro", "corazon", "pulmon", "higado", "rinon", "intestino", "vertebra", "musculo", "tendon", "arteria", "vena", "piel", "unas", "cabello", "sangre", "hueso", "articulacion", "glandula"],

        7 : # Objetos del hogar
            ["sofa", "mesa", "silla", "televisor", "librero", "cama", "lampara", "nevera", "lavadora", "secadora", "cocina", "horno", "microondas", "tostadora", "batidora", "platos", "vasos", "cubiertos", "ollas", "sartenes", "tetera", "cafetera", "taza", "espejo", "cepillo de dientes", "pasta de dientes", "toallas", "ducha", "banera", "inodoro", "lavabo", "escoba", "recogedor", "aspiradora", "cubo de basura", "cortinas", "persianas", "estante", "cajones", "armario", "ropa", "zapatos", "escritorio", "ordenador", "impresora", "telefono", "cargador", "ventana", "puerta", "escaleras"],

        8 : # Prendas de vestir
            ["camiseta", "pantalones", "vestido", "chaqueta", "falda", "camisa", "zapatos", "calcetines", "shorts", "chaqueta de cuero", "blusa", "sombrero", "abrigo", "sueter", "pantalones cortos", "traje", "chaqueta vaquera", "corbata", "gafas de sol", "bufanda", "botas", "chaleco", "mono", "chaqueta deportiva", "traje de bano", "pajarita", "sudadera", "gorra", "guantes", "pantalones de yoga", "chaqueta acolchada", "falda lapiz", "jersey", "top", "pantalones vaqueros", "panuelo", "traje formal", "camiseta sin mangas", "esmoquin", "kimono", "polo", "zapatillas deportivas", "sombrero de paja", "blazer", "chaqueta de esqui", "chaqueta bomber", "vaqueros ajustados", "camiseta de tirantes", "blusa de seda", "chaqueta militar", "vestido de coctel", "chandal", "sudadera con capucha", "camisa hawaiana", "leggings", "chaqueta cortavientos", "vestido de noche", "polo de golf", "chaqueta de punto", "pantalones de traje", "camiseta estampada", "kimono de seda", "cazadora", "blusa de encaje", "mono corto", "pantalones cargo", "tunica", "bermudas", "camiseta de rayas", "vestido maxi"],

        9 : # Generos musicales
            ["rock", "pop", "jazz", "hiphop", "electronica", "reggae", "country", "blues", "salsa", "metal", "folk", "funk", "reggaeton", "clasica", "indie", "rap", "rhythmandblues", "soul", "punk", "dance", "disco", "alternativa", "house", "ranchera", "ska", "latino", "regionalmexicano", "cumbia", "tango", "flamenco", "merengue", "bachata", "vallenato", "samba", "bossanova", "gospel", "grunge", "techno", "trap", "hardrock", "rockandroll", "soul", "jpop", "kpop", "musicaclassica", "opera", "musicafolklorica", "heavymetal", "jazzfusion", "punkrock", "poprock", "musicainstrumental", "musicacountry", "musicaelectronica", "folkrock", "musicaindie", "musicatropical", "musicaurbana", "musicaexperimental", "musicaambiental", "regueton", "mariachi", "bluegrass", "technopop", "triphop", "musicadisco", "generobarroco", "musicaminimalista", "musicamedieval", "musicarenacentista"]
        ,
        10 : # Escritores famosos
            ["williamshakespeare", "janeausten", "charlesdickens", "marktwain", "emilybronte", "fyodordostoevsky", "leotolstoy", "virginiawoolf", "ernesthemingway", "franzkafka", "georgeorwell", "gabrielgarciamarquez", "jorgeluisborges", "migueldecervantes", "marcelproust", "jamesjoyce", "hermannhesse", "victorhugo", "charlottebronte", "agathachristie", "harperlee", "jrrtolkien", "cslewis", "aldoushuxley", "johnsteinbeck", "oscarwilde", "arthurconandoyle", "hgwells", "georgerrmartin", "tonimorrison", "ralphwaldoemerson", "henrydavidthoreau", "waltwhitman", "edgarallanpoe", "homer", "hplovecraft", "fscottfitzgerald", "rudyardkipling", "salmanrushdie", "italocalvino", "albertcamus", "antonchekhov", "dantealighieri", "julesverne", "thomasmann", "josesaramago", "gustaveflaubert", "albertomoravia", "mariovargasllosa", "johnmilton", "samuelbeckett", "paulocoelho", "stefanzweig", "umbertoeco", "williamfaulkner", "kurtvonnegut", "alexandredumas", "hanschristianandersen", "trumancapote", "johnupdike", "margaretatwood", "grahamgreene", "nathanielhawthorne", "sylviaplath", "ernestosabato", "octaviopaz", "isaacasimov", "vladimirnabokov", "yukiomishima", "edithwharton", "emilydickinson", "jackkerouac", "charlesbaudelaire", "mikhailbulgakov", "edgarriceburroughs", "roalddahl", "samueltaylorcoleridge", "wsomersetmaugham", "jorgeamado", "pabloneruda", "tseliot", "jdsalinger", "dorislessing", "mariodeandrade", "jrrmartin", "philipkdick", "whauden", "mariannemoore", "yukiomishima", "rabindranathtagore", "claricelispector", "vikramseth", "kazuoishiguro", "chinuaachebe", "jeanpaulsartre"],

        11 : # Equipos de futbol
            ["real madrid", "barcelona", "manchester united", "bayern munich", "liverpool", "juventus", "paris saint-germain", "chelsea", "manchester city", "arsenal", "ac milan", "inter de milan", "atletico madrid", "borussia dortmund", "tottenham hotspur", "roma", "napoli", "ajax", "benfica", "porto", "boca juniors", "river plate", "flamengo", "santos", "palmeiras", "cruzeiro", "são paulo", "grêmio", "internacional", "corinthians", "colo-colo", "universidad de chile", "américa", "chivas", "pumas", "monterrey", "tigres", "santos laguna", "olimpia", "motagua", "alianza", "fas", "comunicaciones", "municipal", "marathon", "seattle sounders", "los angeles fc", "atlanta united", "new york city fc", "la galaxy", "toronto fc", "montreal impact", "club america", "toluca", "cruz azul", "pachuca", "leon", "tigres uanl", "saprissa", "alajuelense", "herediano", "cartagines", "olimpia", "real espana", "motagua"],

        12 : # Jugadores de Futbol
            ["lionel messi", "cristiano ronaldo", "neymar jr", "kylian mbappe", "robert lewandowski", "mohamed salah", "kevin de bruyne", "sergio ramos", "virgil van dijk", "luka modric", "harry kane", "sadio mane", "manuel neuer", "eden hazard", "antoine griezmann", "paul pogba", "karim benzema", "gareth bale", "david de gea", "sergio aguero", "thiago alcantara", "raheem sterling", "toni kroos", "joshua kimmich", "pierre-emerick aubameyang", "thomas muller", "marc-andre ter stegen", "alisson becker", "romelu lukaku", "jan oblak", "bernardo silva", "angel di maria", "jadon sancho", "marco reus", "son heung-min", "david silva", "sergio busquets", "trent alexander-arnold", "fabinho", "marcelo", "aymeric laporte", "andrew robertson", "hakim ziyech", "heung-min son", "riyad mahrez", "kalidou koulibaly", "ngolo kante", "ciro immobile", "thibaut courtois", "matthijs de ligt", "edinson cavani", "angel correa", "lucas moura", "thomas partey", "dani carvajal", "erling haaland", "douglas costa", "kingsley coman", "koke", "mats hummels", "christian pulisic", "hirving lozano", "alex sandro", "eduardo salvio", "giovani lo celso", "ricardo pereira", "joao cancelo", "diego godin", "vinicius jr", "zlatan ibrahimovic", "aaron wan-bissaka", "wilfried zaha", "andrea belotti", "wissam ben yedder", "dries mertens", "jamie vardy", "romelu lukaku", "alexandre lacazette", "luis suarez", "lautaro martinez", "memphis depay", "pierre-emerick aubameyang", "marcus rashford", "tammy abraham", "bruno fernandes", "serge gnabry", "frenkie de jong", "rodrigo bentancur", "youri tielemans", "jordan henderson"],

        13: #Cantantes famosos
            ["adele", "ariana grande", "beyonce", "bob marley", "bruno mars", "celine dion", "chris brown", "david bowie", "ed sheeran", "elton john", "eminem", "enrique iglesias", "frank sinatra", "freddie mercury", "george michael", "jennifer lopez", "john lennon", "justin bieber", "justin timberlake", "katy perry", "lady gaga", "madonna", "michael jackson", "miley cyrus", "nicki minaj", "prince", "queen", "rihanna", "robbie williams", "sia", "stevie wonder", "taylor swift", "usher", "whitney houston", "adele", "alanis morissette", "alicia keys", "amy winehouse", "avrillavigne", "barbra streisand", "billie eilish", "bjork", "carrie underwood", "celine dion", "cher", "christina aguilera", "cyndi lauper", "demi lovato", "dolly parton", "don omar", "dua lipa", "elvis presley", "florence welch", "gwen stefani", "iggy pop", "james brown", "janis joplin", "jimi hendrix", "joan baez", "joan jett", "johnny cash", "kanye west", "kelly clarkson", "lana del rey", "lenny kravitz", "leonard cohen", "louis armstrong", "ludwig van beethoven", "mariah carey", "mary j blige", "mick jagger", "natalie cole", "nina simone", "paul mccartney", "pink", "prince", "ricky martin", "shakira", "sinead o'connor", "steve wonder", "tina turner", "tony bennett", "tupac shakur", "victor jara", "whitney houston", "willie nelson"],

        14:# Razas de perros
            ["bulldog", "labrador retriever", "golden retriever", "german shepherd", "poodle", "beagle", "boxer", "rottweiler", "dachshund", "siberian husky", "great dane", "chihuahua", "pomeranian", "shih tzu", "yorkshire terrier", "doberman pinscher", "boston terrier", "pug", "border collie", "australian shepherd", "basset hound", "cocker spaniel", "dalmatian", "french bulldog", "italian greyhound", "cavalier king charles spaniel", "english springer spaniel", "bull terrier", "chow chow", "shiba inu", "weimaraner", "vizsla", "west highland white terrier", "papillon", "newfoundland", "rhodesian ridgeback", "bichon frise", "shetland sheepdog", "staffordshire bull terrier", "afghan hound", "akita", "american bulldog", "american eskimo dog", "american staffordshire terrier", "basenji", "bloodhound", "borzoi", "brittany spaniel", "brussels griffon", "bullmastiff", "chinese crested", "clumber spaniel", "corgi", "english bulldog", "english cocker spaniel", "english setter", "english toy spaniel", "giant schnauzer", "gordon setter", "havanese", "irish setter", "irish wolfhound", "japanese chin", "keeshond", "komondor", "kuvasz", "leonberger", "lhasa apso", "maltese", "miniature pinscher", "newfoundland", "norfolk terrier", "norwegian elkhound", "old english sheepdog", "otterhound", "papillon", "pekingese", "pembroke welsh corgi", "pharaoh hound", "pointer", "pomeranian", "poodle", "portuguese water dog", "redbone coonhound", "saluki", "samoyed", "schipperke", "scottish terrier", "shetland sheepdog", "shih tzu", "siberian husky", "silky terrier", "skye terrier", "soft coated wheaten terrier", "staffordshire bull terrier", "standard schnauzer", "vizsla", "weimaraner", "welsh springer spaniel", "west highland white terrier", "whippet", "wirehaired pointing griffon"],

        15:#Utiles Escolares
            ["lapiz", "pluma", "cuaderno", "libro", "goma de borrar", "regla", "tijeras", "pegamento", "calculadora", "mochila", "marcadores", "compas", "lapicero", "papel", "lapices de colores", "carpeta", "borrador", "pincel", "cinta adhesiva", "libreta", "subrayadores", "corrector", "esferos", "postits", "agenda", "grapadora", "papel de calcar", "cartulina", "lamina de acetato", "cartuchos de tinta", "resaltadores", "temperas", "borrador de tinta", "punta de recambio para boligrafo", "sacapuntas", "lapicera", "libros de referencia", "tijeras de precision", "agenda escolar", "compas escolar", "goma de borrar blanca", "maquina de escribir", "calendario", "fichas de estudio", "calculadora cientifica", "puntero laser", "estuche", "pizarra blanca", "borrador de pizarra", "carpetas de plastico", "etiquetas adhesivas"],

        16:#peliculas famosas
            ["el padrino", "el senor de los anillos: el retorno del rey", "casablanca", "titanic", "el rey leon", "pulp fiction", "forrest gump", "el caballero de la noche", "la lista de schindler", "el gran dictador", "ciudadano kane", "cadena perpetua", "matrix", "el club de la pelea", "regreso al futuro", "la vida es bella", "el silencio de los corderos", "star wars: episodio iv - una nueva esperanza", "apocalipsis ahora", "gladiador", "avatar", "el resplandor", "memento", "intocable", "el sexto sentido", "inception", "el pianista", "el bueno, el malo y el feo", "el exorcista", "el gran gatsby", "la la land", "el viaje de chihiro", "buenos muchachos", "el lobo de wall street", "el senor de los anillos: la comunidad del anillo", "ratatouille", "el padrino: parte ii", "el rey leon", "el club de los cinco", "reservoir dogs", "la naranja mecanica", "el renacido", "piratas del caribe: la maldicion del perla negra", "el curioso caso de benjamin button", "el aviador", "los siete samurais", "cantando bajo la lluvia", "blade runner", "el gran lebowski", "taxi driver", "el septimo sello", "psicosis", "cinema paradiso", "el golpe", "el laberinto del fauno", "el graduado", "cisne negro", "el club de la pelea", "el resplandor", "la vida de los otros", "el ilusionista", "la princesa prometida", "el viaje de chihiro", "la guerra de las galaxias: episodio v - el imperio contraataca", "inception", "el gran dictador", "gladiador", "la trilogia de el senor de los anillos"],

        17: # Pokemon
            ["Pikachu", "Charizard", "Mewtwo", "Mew", "Gyarados", "Dragonite", "Blastoise", "Venusaur","Arcanine", "Alakazam", "Gengar", "Jolteon", "Flareon", "Vaporeon", "Lapras", "Snorlax", "Tyranitar", "Ampharos", "Espeon", "Umbreon", "Scizor" , "Blaziken", "Swampert", "Sceptile", "Gardevoir", "Salamence", "Metagross", "Aggron", "Groudon","Kyogre", "Rayquaza", "Latios", "Latias", "Breloom", "Flygon", "Altaria", "Absol", "Manectric","Sharpedo", "Infernape", "Empoleon", "Torterra", "Lucario", "Garchomp", "Roserade", "Staraptor", "Luxray","Dialga", "Palkia", "Gallade", "Magnezone", "Togekiss", "Weavile", "Yanmega", "Honchkrow","Gastrodon", "Rhyperior", "Electivire", "Magmortar", "Leafeon", "Glaceon", "Mamoswine", "Tangrowth","Dusknoir", "Froslass", "Samurott", "Emboar", "Serperior", "Zoroark", "Hydreigon", "Galvantula", "Krookodile", "Cofagrigus","Chandelure", "Haxorus", "Volcarona", "Eelektross", "Carracosta", "Archeops", "Excadrill", "Bisharp","Mandibuzz", "Braviary","Greninja", "Delphox", "Chesnaught", "Talonflame", "Aegislash", "Hawlucha", "Goodra", "Noivern","Sylveon", "Aurorus", "Tyrantrum", "Malamar", "Barbaracle"]
            }
    elif idioma==2: 
        lista = {


        1 : #Fruits
            ["blueberry", "raspberry", "strawberry", "currant", "lemon", "tangerine", "orange", "grapefruit", "avocado", "starfruit", "cherimoya", "coconut", "date", "kiwi", "mango", "papaya", "pineapple", "banana", "cherry", "plum", "persimmon", "apple", "peach", "loquat", "pear", "grape", "almond", "hazelnut", "peanut", "chestnut", "walnut"] ,
                    
        2 : #Superheroes
            ["antman", "aquaman", "atom", "batgirl", "batman", "blackpanther", "blackwidow", "blade", "bluebeetle", "booster", "cable", "captainamerica", "captainmarvel", "catwoman", "colossus", "cyclops", "daredevil", "deadpool", "doctorfate", "doctorstrange", "elektra", "falcon", "firestorm", "flash", "gambit", "ghostrider", "greenarrow", "greenlantern", "groot", "hawkeye", "hellboy", "hulk", "humantorch", "huntress", "iceman", "invisiblewoman", "ironfist", "ironman", "jeangrey", "joker", "jubilee", "juggernaut", "kittypryde", "loki", "lukecage", "magneto", "martianmanhunter", "misterfantastic", "moonknight", "msmarvel", "mystique", "namorita", "nightcrawler", "nightwing", "nova", "omegared", "phoenix", "plasticman", "poisonivy", "powergirl", "professorxavier", "psylocke", "punisher", "quicksilver", "raven", "redhood", "robin", "rocketeer", "rogue", "sabretooth", "scarletwitch", "shadowcat", "shazam", "shehulk", "silversurfer", "spiderman", "starfire", "storm", "submariner", "supergirl", "superman", "swampthing", "thing", "thor", "tigra", "venom", "vision", "warmachine", "wasp", "watchmen", "wolverine", "wonderwoman", "zatanna"] ,      
            
        3 : #Animals
            ["dog", "cat", "elephant", "giraffe", "lion", "tiger", "wolf", "bear", "zebra", "hippopotamus","rhinoceros","cow","sheep","pig","rabbit","mouse","squirrel","duck","turkey","hen","rooster","bird","parrot","penguin","turtle","crocodile","snake","lizard","chameleon","frog","toad","shark","whale","dolphin","fish","horse","donkey","zebra","ostrich","kangaroo","koala","panda","camel","ant","bee","spider","beetle","butterfly","mosquito"],

        4 : #Countries
            ["Argentina", "Australia", "Brazil", "Canada", "China","Colombia","Egypt","Spain","United States","France","India","England","Italy","Japan","Mexico","Peru","Russia","South Africa","Switzerland","Thailand","Turkey","Uruguay","Venezuela","Germany","Saudi Arabia","Belgium","Chile","Denmark","Ecuador","Philippines","Greece","Netherlands","Indonesia","Ireland","Israel","Kenya","Malaysia","Norway","New Zealand","Panama","Poland","Portugal", "Czech Republic", "Singapore", "Sweden", "Vietnam", "Cuba", "Costa Rica", "Honduras", "Nicaragua"],

        5: # Means of transportation
            ["car", "truck", "motorcycle", "bicycle", "bus", "tricycle", "carriage", "van", "trailer", "train", "tram", "boat", "yacht", "airplane", "helicopter", "race car", "van", "RV", "skateboard", "crane", "excavator", "ambulance", "snowmobile", "wheelbarrow", "golf cart", "tractor", "Segway", "firetruck", "sled", "seaplane", "horse-drawn carriage", "tank", "submarine", "quad", "armored car", "trailer", "scooter", "hovercraft", "tuk-tuk", "tank", "mobile crane", "school bus", "jet ski", "hot air balloon", "trolley", "mototaxi", "ice cream truck", "autogyro", "delivery truck", "bullet train"],

        6: # Parts of the body
            ["head", "neck", "shoulder", "arm", "elbow", "wrist", "hand", "finger", "thumb", "chest", "back", "stomach", "waist", "hip", "leg", "knee", "ankle", "foot", "heel", "toe", "eye", "eyebrow", "eyelid", "nose", "ear", "lip", "tooth", "chin", "cheek", "tongue", "jaw", "brain", "heart", "lung", "liver", "kidney", "intestine", "vertebra", "muscle", "tendon", "artery", "vein", "skin", "nail", "hair", "blood", "bone", "joint", "gland"],

        7: # Household objects
            ["sofa", "table", "chair", "television", "bookshelf", "bed", "lamp", "refrigerator", "washing machine", "dryer", "kitchen", "oven", "microwave", "toaster", "blender", "plates", "glasses", "silverware", "pots", "pans", "kettle", "coffee maker", "cup", "mirror", "toothbrush", "toothpaste", "towels", "shower", "bathtub", "toilet", "sink", "broom", "dustpan", "vacuum cleaner", "trash can", "curtains", "blinds", "shelf", "drawers", "wardrobe", "clothes", "shoes", "desk", "computer", "printer", "telephone", "charger", "window", "door", "stairs"],

        8: # Clothing
            ["t-shirt", "pants", "dress", "jacket", "skirt", "shirt", "shoes", "socks", "shorts", "leather jacket", "blouse", "hat", "coat", "sweater", "shorts", "suit", "denim jacket", "tie", "sunglasses", "scarf", "boots", "vest", "jumpsuit", "sports jacket", "swimsuit", "bowtie", "hoodie", "cap", "gloves", "yoga pants", "padded jacket", "pencil skirt", "sweatshirt", "top", "jeans", "scarf", "formal suit", "tank top", "tuxedo", "kimono", "polo shirt", "sneakers", "straw hat", "blazer", "ski jacket", "bomber jacket", "skinny jeans", "tank top", "silk blouse", "military jacket", "cocktail dress", "tracksuit", "hooded sweatshirt", "hawaiian shirt", "leggings", "windbreaker", "evening dress", "golf polo", "knit jacket", "suit pants", "printed t-shirt", "silk kimono", "jacket", "lace blouse", "short jumpsuit", "cargo pants", "tunic", "bermuda shorts", "striped t-shirt", "maxi dress"],

        9 : # Generos musicales
            ["rock", "pop", "jazz", "hiphop", "electronica", "reggae", "country", "blues", "salsa", "metal", "folk", "funk", "reggaeton", "clasica", "indie", "rap", "rhythmandblues", "soul", "punk", "dance", "disco", "alternativa", "house", "ranchera", "ska", "latino", "regionalmexicano", "cumbia", "tango", "flamenco", "merengue", "bachata", "vallenato", "samba", "bossanova", "gospel", "grunge", "techno", "trap", "hardrock", "rockandroll", "soul", "jpop", "kpop", "musicaclassica", "opera", "musicafolklorica", "heavymetal", "jazzfusion", "punkrock", "poprock", "musicainstrumental", "musicacountry", "musicaelectronica", "folkrock", "musicaindie", "musicatropical", "musicaurbana", "musicaexperimental", "musicaambiental", "regueton", "mariachi", "bluegrass", "technopop", "triphop", "musicadisco", "generobarroco", "musicaminimalista", "musicamedieval", "musicarenacentista"]
        ,
        10 : # Escritores famosos
            ["williamshakespeare", "janeausten", "charlesdickens", "marktwain", "emilybronte", "fyodordostoevsky", "leotolstoy", "virginiawoolf", "ernesthemingway", "franzkafka", "georgeorwell", "gabrielgarciamarquez", "jorgeluisborges", "migueldecervantes", "marcelproust", "jamesjoyce", "hermannhesse", "victorhugo", "charlottebronte", "agathachristie", "harperlee", "jrrtolkien", "cslewis", "aldoushuxley", "johnsteinbeck", "oscarwilde", "arthurconandoyle", "hgwells", "georgerrmartin", "tonimorrison", "ralphwaldoemerson", "henrydavidthoreau", "waltwhitman", "edgarallanpoe", "homer", "hplovecraft", "fscottfitzgerald", "rudyardkipling", "salmanrushdie", "italocalvino", "albertcamus", "antonchekhov", "dantealighieri", "julesverne", "thomasmann", "josesaramago", "gustaveflaubert", "albertomoravia", "mariovargasllosa", "johnmilton", "samuelbeckett", "paulocoelho", "stefanzweig", "umbertoeco", "williamfaulkner", "kurtvonnegut", "alexandredumas", "hanschristianandersen", "trumancapote", "johnupdike", "margaretatwood", "grahamgreene", "nathanielhawthorne", "sylviaplath", "ernestosabato", "octaviopaz", "isaacasimov", "vladimirnabokov", "yukiomishima", "edithwharton", "emilydickinson", "jackkerouac", "charlesbaudelaire", "mikhailbulgakov", "edgarriceburroughs", "roalddahl", "samueltaylorcoleridge", "wsomersetmaugham", "jorgeamado", "pabloneruda", "tseliot", "jdsalinger", "dorislessing", "mariodeandrade", "jrrmartin", "philipkdick", "whauden", "mariannemoore", "yukiomishima", "rabindranathtagore", "claricelispector", "vikramseth", "kazuoishiguro", "chinuaachebe", "jeanpaulsartre"],

        11 : # Equipos de futbol
            ["real madrid", "barcelona", "manchester united", "bayern munich", "liverpool", "juventus", "paris saint-germain", "chelsea", "manchester city", "arsenal", "ac milan", "inter de milan", "atletico madrid", "borussia dortmund", "tottenham hotspur", "roma", "napoli", "ajax", "benfica", "porto", "boca juniors", "river plate", "flamengo", "santos", "palmeiras", "cruzeiro", "são paulo", "grêmio", "internacional", "corinthians", "colo-colo", "universidad de chile", "américa", "chivas", "pumas", "monterrey", "tigres", "santos laguna", "olimpia", "motagua", "alianza", "fas", "comunicaciones", "municipal", "marathon", "seattle sounders", "los angeles fc", "atlanta united", "new york city fc", "la galaxy", "toronto fc", "montreal impact", "club america", "toluca", "cruz azul", "pachuca", "leon", "tigres uanl", "saprissa", "alajuelense", "herediano", "cartagines", "olimpia", "real espana", "motagua"],

        12 : # Jugadores de Futbol
            ["lionel messi", "cristiano ronaldo", "neymar jr", "kylian mbappe", "robert lewandowski", "mohamed salah", "kevin de bruyne", "sergio ramos", "virgil van dijk", "luka modric", "harry kane", "sadio mane", "manuel neuer", "eden hazard", "antoine griezmann", "paul pogba", "karim benzema", "gareth bale", "david de gea", "sergio aguero", "thiago alcantara", "raheem sterling", "toni kroos", "joshua kimmich", "pierre-emerick aubameyang", "thomas muller", "marc-andre ter stegen", "alisson becker", "romelu lukaku", "jan oblak", "bernardo silva", "angel di maria", "jadon sancho", "marco reus", "son heung-min", "david silva", "sergio busquets", "trent alexander-arnold", "fabinho", "marcelo", "aymeric laporte", "andrew robertson", "hakim ziyech", "heung-min son", "riyad mahrez", "kalidou koulibaly", "ngolo kante", "ciro immobile", "thibaut courtois", "matthijs de ligt", "edinson cavani", "angel correa", "lucas moura", "thomas partey", "dani carvajal", "erling haaland", "douglas costa", "kingsley coman", "koke", "mats hummels", "christian pulisic", "hirving lozano", "alex sandro", "eduardo salvio", "giovani lo celso", "ricardo pereira", "joao cancelo", "diego godin", "vinicius jr", "zlatan ibrahimovic", "aaron wan-bissaka", "wilfried zaha", "andrea belotti", "wissam ben yedder", "dries mertens", "jamie vardy", "romelu lukaku", "alexandre lacazette", "luis suarez", "lautaro martinez", "memphis depay", "pierre-emerick aubameyang", "marcus rashford", "tammy abraham", "bruno fernandes", "serge gnabry", "frenkie de jong", "rodrigo bentancur", "youri tielemans", "jordan henderson"],

        13: #Cantantes famosos
            ["adele", "ariana grande", "beyonce", "bob marley", "bruno mars", "celine dion", "chris brown", "david bowie", "ed sheeran", "elton john", "eminem", "enrique iglesias", "frank sinatra", "freddie mercury", "george michael", "jennifer lopez", "john lennon", "justin bieber", "justin timberlake", "katy perry", "lady gaga", "madonna", "michael jackson", "miley cyrus", "nicki minaj", "prince", "queen", "rihanna", "robbie williams", "sia", "stevie wonder", "taylor swift", "usher", "whitney houston", "adele", "alanis morissette", "alicia keys", "amy winehouse", "avrillavigne", "barbra streisand", "billie eilish", "bjork", "carrie underwood", "celine dion", "cher", "christina aguilera", "cyndi lauper", "demi lovato", "dolly parton", "don omar", "dua lipa", "elvis presley", "florence welch", "gwen stefani", "iggy pop", "james brown", "janis joplin", "jimi hendrix", "joan baez", "joan jett", "johnny cash", "kanye west", "kelly clarkson", "lana del rey", "lenny kravitz", "leonard cohen", "louis armstrong", "ludwig van beethoven", "mariah carey", "mary j blige", "mick jagger", "natalie cole", "nina simone", "paul mccartney", "pink", "prince", "ricky martin", "shakira", "sinead o'connor", "steve wonder", "tina turner", "tony bennett", "tupac shakur", "victor jara", "whitney houston", "willie nelson"],
                    
        14:# Razas de perros
            ["bulldog", "labrador retriever", "golden retriever", "german shepherd", "poodle", "beagle", "boxer", "rottweiler", "dachshund", "siberian husky", "great dane", "chihuahua", "pomeranian", "shih tzu", "yorkshire terrier", "doberman pinscher", "boston terrier", "pug", "border collie", "australian shepherd", "basset hound", "cocker spaniel", "dalmatian", "french bulldog", "italian greyhound", "cavalier king charles spaniel", "english springer spaniel", "bull terrier", "chow chow", "shiba inu", "weimaraner", "vizsla", "west highland white terrier", "papillon", "newfoundland", "rhodesian ridgeback", "bichon frise", "shetland sheepdog", "staffordshire bull terrier", "afghan hound", "akita", "american bulldog", "american eskimo dog", "american staffordshire terrier", "basenji", "bloodhound", "borzoi", "brittany spaniel", "brussels griffon", "bullmastiff", "chinese crested", "clumber spaniel", "corgi", "english bulldog", "english cocker spaniel", "english setter", "english toy spaniel", "giant schnauzer", "gordon setter", "havanese", "irish setter", "irish wolfhound", "japanese chin", "keeshond", "komondor", "kuvasz", "leonberger", "lhasa apso", "maltese", "miniature pinscher", "newfoundland", "norfolk terrier", "norwegian elkhound", "old english sheepdog", "otterhound", "papillon", "pekingese", "pembroke welsh corgi", "pharaoh hound", "pointer", "pomeranian", "poodle", "portuguese water dog", "redbone coonhound", "saluki", "samoyed", "schipperke", "scottish terrier", "shetland sheepdog", "shih tzu", "siberian husky", "silky terrier", "skye terrier", "soft coated wheaten terrier", "staffordshire bull terrier", "standard schnauzer", "vizsla", "weimaraner", "welsh springer spaniel", "west highland white terrier", "whippet", "wirehaired pointing griffon"],
                
        15:#School Supplies
            ["pencil", "pen", "notebook", "book", "eraser", "ruler", "scissors", "glue", "calculator", "backpack", "markers", "compass", "ballpoint pen", "paper", "colored pencils", "folder", "chalkboard eraser", "paintbrush", "tape", "notepad", "highlighters", "correction fluid", "pens", "sticky notes", "planner", "stapler", "tracing paper", "cardboard", "acetate sheet", "ink cartridges", "highlighters", "tempera paints", "ink eraser", "pen refill", "pencil sharpener", "ink pen", "reference books", "precision scissors", "student planner", "white eraser", "typewriter", "calendar", "study cards", "scientific calculator", "laser pointer", "pencil case", "whiteboard", "whiteboard eraser", "plastic folders", "adhesive labels"],    
        
        16: # Pokemon
            ["Pikachu", "Charizard", "Mewtwo", "Mew", "Gyarados", "Dragonite", "Blastoise", "Venusaur","Arcanine", "Alakazam", "Gengar", "Jolteon", "Flareon", "Vaporeon", "Lapras", "Snorlax", "Tyranitar", "Ampharos", "Espeon", "Umbreon", "Scizor" , "Blaziken", "Swampert", "Sceptile", "Gardevoir", "Salamence", "Metagross", "Aggron", "Groudon","Kyogre", "Rayquaza", "Latios", "Latias", "Breloom", "Flygon", "Altaria", "Absol", "Manectric","Sharpedo", "Infernape", "Empoleon", "Torterra", "Lucario", "Garchomp", "Roserade", "Staraptor", "Luxray","Dialga", "Palkia", "Gallade", "Magnezone", "Togekiss", "Weavile", "Yanmega", "Honchkrow","Gastrodon", "Rhyperior", "Electivire", "Magmortar", "Leafeon", "Glaceon", "Mamoswine", "Tangrowth","Dusknoir", "Froslass", "Samurott", "Emboar", "Serperior", "Zoroark", "Hydreigon", "Galvantula", "Krookodile", "Cofagrigus","Chandelure", "Haxorus", "Volcarona", "Eelektross", "Carracosta", "Archeops", "Excadrill", "Bisharp","Mandibuzz", "Braviary","Greninja", "Delphox", "Chesnaught", "Talonflame", "Aegislash", "Hawlucha", "Goodra", "Noivern","Sylveon", "Aurorus", "Tyrantrum", "Malamar", "Barbaracle"]
            }
        
    return lista
```
</p></details></br>

+ def elegirpalabra():
<details><summary> Funcion :</summary><p> 
  
``` python
  def elegirpalabra(lista, y):
    """
    Esta función elige una palabra al azar de una lista y la devuelve en mayúsculas.

    Args:
        lista (dict): Una diccionario de palabras de la cual se seleccionará una al azar.
        y (int): El índice o posición dentro de la lista desde donde se elige la palabra, definido por el usuario.

    Returns:
        str: La palabra seleccionada al azar de la lista, en mayúsculas.
    """
    Epalabra = (random.choice(lista[y])).upper()
    return Epalabra
  ```
</p></details></br>

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
