# Bienvenidas al Workshop Backend de Ada

El contenido de este documento tiene por finalidad ayudarte arealizar el ejercicio que se desarrollará en la ultima parte del workshop, lo unico que debes hacer es seguir las indicaciones del instructor al momento de realizar cada paso.

## Requerimientos previos

Antes de iniciar la practica, debe tener lo siguiente:
 
- Una cuenta creada en el respositorio [**GitHub**](https://github.com/)
- Una cuenta creada en [**GitPod**](https://www.gitpod.io/), esta se crea con la cuenta de **GitHub**
- Instalar  [**GitPod browser-extension**](https://www.gitpod.io/docs/browser-extension/) en tu navegador.

# Vamos al codigo

> **Nota:** Es importante comprender que todo lo que se desarrolle en la practica, tiene como finalidad exponer el tipo de aplicacion que se logrará desarrollar al realizar el curso **Backend Java de Ada** y no entender plenamente cada elemento del codigo de la aplicacion a demostrar.

## Configuracion del IDE

Antes de empezar a realizar el codigo, es necesario instalar una extension en el ide para que este no muestre un error de una libreria que se usa en el proyecto.

Para realizar esta instalacion, vamos a la seccion de `Extensisons` y en el buscador escribimos `Lombok Annotations`. 

Se mostrará una serie de opciones e instalamos la que tiene por nombre :hot_pepper: `Lombok Annotations Support for VS Code`. 

Nos pregutará si queremeos instalarlo globalmente o en el proyecto, selecionar en el proyecto.

y listo! ya esta configurado el IDE.

## database.json

    [
      {
        "id": 1,
        "title": "Bad Boys para siempre",
        "year": 2020,
        "type": "pelicula",
        "gender": "Comedia y accion",
        "imageUrl": "https://cineenlinea.net/wp-content/uploads/2020/01/Poster-Bad-Boys-3.jpg"
      },
      {
        "id": 2,
        "title": "El Stand de los besos",
        "year": 2020,
        "type": "pelicula",
        "gender": "Comedia romántica adolescente",
        "imageUrl": "https://upload.wikimedia.org/wikipedia/en/c/c8/The_Kissing_Booth_2_poster.jpg"
      },
      {
        "id": 3,
        "title": "Joker",
        "year": 2019,
        "type": "pelicula",
        "gender": "Suspenso y drama psicológico",
        "imageUrl": "https://pics.filmaffinity.com/Joker-790658206-mmed.jpg"
      },
      {
        "id": 4,
        "title": "It 2",
        "year": 2019,
        "type": "pelicula",
        "gender": "Terror sobrenatural",
        "imageUrl": "https://es.web.img3.acsta.net/pictures/19/07/30/09/09/0763744.jpg"
      },
      {
        "id": 5,
        "title": "The Umbrella Academy",
        "year": 2019,
        "type": "serie",
        "gender": "Accion y Aventura",
        "imageUrl": "https://pics.filmaffinity.com/The_Umbrella_Academy_Serie_de_TV-422973449-mmed.jpg"
      },
      {
        "id": 6,
        "title": "The Rain",
        "year": 2018,
        "type": "serie",
        "gender": "Accion",
        "imageUrl": "https://miro.medium.com/max/640/1*NRtDqM7d-ZEiHUaHNySjRQ.jpeg"
      },
      {
        "id": 7,
        "title": "Dark",
        "year": 2017,
        "type": "serie",
        "gender": "Ciencia ficción",
        "imageUrl": "https://www.awesomepostersonline.com/uploads/2018-06-01/b1fb1ea4/f336f3fb80e.jpg"
      },
      {
        "id": 8,
        "title": "Star Wars: The Last Jedi",
        "year": 2017,
        "type": "pelicula",
        "gender": "Ciencia ficción",
        "imageUrl": "https://i.pinimg.com/originals/26/a8/ab/26a8ab88a1ae4386ef6c051dbbe8b2ed.jpg"
      },
      {
        "id": 9,
        "title": "Scream ",
        "year": 2015,
        "type": "serie",
        "gender": "Terror",
        "imageUrl": "https://pics.filmaffinity.com/scream_resurrection-304764663-large.jpg"
      },
      {
        "id": 10,
        "title": "Juego de tronos",
        "year": 2011,
        "type": "serie",
        "gender": "Drama y fantasía medieval",
        "imageUrl": "https://www.eltiempo.com/files/image_640_428/uploads/2019/05/23/5ce6e2a1369e8.jpeg"
      },
      {
        "id": 11,
        "title": "El precio del mañana",
        "year": 2011,
        "type": "pelicula",
        "gender": "Ciencia ficción distópica y suspenso",
        "imageUrl": "https://i.ytimg.com/vi/PT99JkrtkMo/hqdefault.jpg"
      },
      {
        "id": 12,
        "title": "CSI: Miami",
        "year": 2002,
        "type": "serie",
        "gender": "acción",
        "imageUrl": "https://imagenes.gatotv.com/categorias/programas/posters/csi_miami.jpg"
      },
      {
        "id": 13,
        "title": "Harry Potter y la cámara secreta",
        "year": 2002,
        "type": "pelicula",
        "gender": "Ciencia ficción",
        "imageUrl": "https://assets.cinepolisklic.com/images/ae0dacc3e95640ec8a3974efba7fe57d_250X375.jpg"
      },
      {
        "id": 14,
        "title": "Friends",
        "year": 1994,
        "type": "serie",
        "gender": "Comedia",
        "imageUrl": "https://pics.filmaffinity.com/Friends_Serie_de_TV-875463197-large.jpg"
      },
      {
        "id": 15,
        "title": "Miami Vice",
        "year": 1990,
        "type": "serie",
        "gender": "Accion",
        "imageUrl": "https://static.motor.es/fotos-noticias/2020/04/ferrari-365-gts4-daytona-spyder-miami-vice-corrupcion-en-miami-202066850-1587743709_1.jpg"
      },
      {
        "id": 16,
        "title": "Casablanca",
        "year": 1942,
        "type": "pelicula",
        "gender": "Drama y romance ",
        "imageUrl": "https://lavozenoffdotnet.files.wordpress.com/2013/03/c00.jpg?w=640"
      }
    ]

## MovieOrSerie.java

    package  ada.workshop.backend;
    
    import  lombok.Getter;
    import  lombok.NoArgsConstructor;
    import  lombok.Setter;
    
    @Getter @Setter
    @NoArgsConstructor
    public  class  MovieOrSerie {
    
        private  Long id;
        private  String title;
        private  Integer year;
        private  String type;
        private  String gender;
        private  String imageUrl;
    
    }

## MainController.java

    package ada.workshop.backend;
    
    import java.io.File;
    import java.util.ArrayList;
    import java.util.List;
    import java.util.Optional;
    import java.util.function.Predicate;
    import java.util.stream.Collectors;
    
    import com.fasterxml.jackson.core.type.TypeReference;
    import com.fasterxml.jackson.databind.ObjectMapper;
    
    import org.springframework.http.ResponseEntity;
    import org.springframework.web.bind.annotation.CrossOrigin;
    import org.springframework.web.bind.annotation.GetMapping;
    import org.springframework.web.bind.annotation.RequestParam;
    import org.springframework.web.bind.annotation.RestController;
    
    
    @RestController
    public class MainController {
    
        @GetMapping({ "", "/" }) @CrossOrigin(origins = "*")
        public ResponseEntity<List<MovieOrSerie>> getAllMoviesOrSeries(
                @RequestParam Optional<Integer> year,
                @RequestParam Optional<String> type ) throws Exception {
    
            List<MovieOrSerie> movieOrSeriesFromDatabase = gatDataFromDatabaseFake();
    
            List<MovieOrSerie> movieOrSeries = movieOrSeriesFromDatabase
                    .stream()
                    .filter(getFilterRules(year, type))
                    .collect(Collectors.toList());
    
            return ResponseEntity.ok(movieOrSeries);
        }
    
        public List<MovieOrSerie> gatDataFromDatabaseFake() throws Exception {
            ObjectMapper mapper = new ObjectMapper();
            return mapper.readValue(
                new File("database.json"),
                new TypeReference<List<MovieOrSerie>>() {
            });
        }
    
        private Predicate<MovieOrSerie> getFilterRules(Optional<Integer> yearOpt, Optional<String> typeOpt) {
            List<Predicate<MovieOrSerie>> filterConditions = new ArrayList<>();
    
            yearOpt.ifPresent(year -> filterConditions.add(mos -> mos.getYear().equals(year)));
            typeOpt.ifPresent(type -> filterConditions.add(mos -> mos.getType().equals(type)));
    
            return filterConditions.stream().reduce(mos -> true, Predicate::and);
        }
    }

# Observaciones

Si el IDE online no muestra las opciones de `Run | Debug` en la clase `BackendApplication`, solo debemos copiar y pegar en la terminal esta linea de codigo: `mvn spring-boot:run`, con esto se pone el marcha la applicacion.