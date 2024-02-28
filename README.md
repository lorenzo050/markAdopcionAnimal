# Proyecto adopción animal LinkAPet
Proyecto web adopcion animal

* Es una App / Web que ayuda a la adopción animal
* Es accesible principalmente desde los dispositivos móviles 
* Permite publicar anuncios de animales sin hogar
* Fotos de los animales generadas automáticamente

## Instalación del proyecto
1. Tener angular y npm instalados
2. Clonar proyecto
3. npm instal -> descargar paquetes de node automaticamente
4. Clonar base de datos en phpMyAdmin

## Ejecución del proyecto
1. Ejecutar base de datos PhpMyAdmin (se ejecuta con un servidor en localhost como xamp)
2. Ejetuar archivo de API.php para poder acceder a la BD
3. ionic serve desde la ruta del proyecto
4. Abrir pestaña navegador de localhost

## Lenguajes/herramientas usadas
- Ionic Framework
- Angular (Standalone)
- TypeScript
- SCSS
- PHP
- SQL
- phpMyAdmin
- Visual Studio Code
- XAMP
- Android Studio

## Estructura y componentes
Para cada página he creado un page y si su contenido puede ser reutilizable he crado un componente asociado a esta 

![img](/imgCanva/img2.png) ![img](/imgCanva/img1.png)

Y llamo al componente dentro del html con sus importaciones correspondientes
![img](/imgCanva/img4.png)

Estructuracion completa de la web
![img](/imgCanva/img5.png)

## Ngif
![img](/imgCanva/img8.png)

## Ngswitch
![img](/imgCanva/img6.png)

## NgFor
![img](/imgCanva/img4.png)

## Interface 
![img](/imgCanva/img9.png)
![img](/imgCanva/img10.png)

## API
He usado la api de https://dog.ceo/dog-api/ para conseguir las fotos de los perros automatica y aleatoriamente
![img](/imgCanva/api.png)

## Ventanas emergentes
Ventana emergente mediante AlertController
![img](/imgCanva/img12.png)

# Estilos e interfaces visuales
Ejemplo estilos card principal
```scss
.card-style {
  color: white;
}
.card-div-img {
  padding-right: 15px;
  padding-left: 15px;
  position: relative;
}
.card-img {
  border: 3px solid #ffffff;
  border-radius: 15px;
  width: 250px;
  height: 150px;
}
.card-badge {
  position: absolute;
  right: 15px;
  top: 128px;
}
.card-text-accion {
  color: black;
  background-color: white;
  padding: 4px;
  border-radius: 15px;
}
.card-dog {
  border-radius: 15px;
}
.card-dog:hover {
  background-color: #597FCB;
  box-shadow: 3px 3px 8px 4px rgba(0, 0, 0, 0.67);
}
.card-icon-tipoAdop {
  margin-right: 10px;
}
```

Edicion .scss de componentes Ionic
```scss
.btn-edit-2{
  --background: #white;
  --background-hover: #9ce0be;
  --background-activated: #88f4be;
  --background-focused: #88f4be;
  --color: #7d9ee0;
  --border-radius: 25px;
  --border-color: #7d9ee0;
  --border-style: solid;
  --border-width: 3px;
  --box-shadow: 0 2px 6px 0 rgb(0, 0, 0, 0.25);
  --ripple-color: blue;
  --padding-top: 1em;
  --padding-bottom: 1em;
  --padding-start: 3em;
  --padding-end: 3em;
}
```



Variables .scss Ionic
Variables reutilizables
```scss
  /** color-principal LORENZO **/
  --ion-color-color-principal: #7D9EE0;
	--ion-color-color-principal-rgb: 125,158,224;
	--ion-color-color-principal-contrast: #000000;
	--ion-color-color-principal-contrast-rgb: 255,255,255,255;
	--ion-color-color-principal-shade: #6e8bc5;
	--ion-color-color-principal-tint: #8aa8e3;
```

```javascript
<ion-tab-bar color="color-principal" slot="bottom">
```

## Interfaces visuales
Pagina adopcion Ordenador
|  Ordenador  | Tablet | Movil| 
| ------------- | ------------- | ------------ | 
| ![img](/imgCanva/img15.png)  | ![img](/imgCanva/img17.png)  | ![img](/imgCanva/img16.png) |

Perfil animal
|  Ordenador  | Movil | Movil| 
| ------------- | ------------- | ------------ | 
| ![img](/imgCanva/img18.png)  | ![img](/imgCanva/perfilperro.png)  | ![img](/imgCanva/img19.png) |

Perfil 
|  Ordenador  | Movil | Movil| 
| ------------- | ------------- | ------------ | 
| ![img](/imgCanva/img21.png)  | ![img](/imgCanva/img20.png)  | ![img](/imgCanva/miperfil.png) |

## Funciones adicionales
- Aplicacion instalada y ejecutada desde dispositivo android
![img](/imgCanva/capturamovil.png)

- Uso de base de datos mediante PHP, phpMyAdmin. Todo el acceso a BD mediante un archivo funcionando como API
Ejemplo:
```php
if ($db) {
                $sql = "INSERT INTO `usuarios`(`email`, `password`, `nombre`, `telefono`, `ubicacion`, `tipoUser`) 
                VALUES (?,?,?,?,?,?)";
                $prepared_statement = $db->prepare($sql);
                $resultado = $prepared_statement->execute([$email, $password, $nombre, $telefono, $ubicacion, $tipoUser]);

                // Verificar si la inserción fue exitosa
                if ($resultado) {
                    $respuesta = array("mensaje" => "Insercion exitosa");
                } else {
                    $respuesta = array("mensaje" => "Error en la insercion");
                }

                $json_resultados = json_encode($respuesta);

                echo $json_resultados;
                //fin de comprobar
            } else {
                echo "Error: No se pudo conectar a la base de datos.";
            }
        } catch (PDOException $e) {
            // Manejar la excepción en caso de algún otro error relacionado con la base de datos
            echo "Error de base de datos: " . $e->getMessage();
        } catch (Exception $e) {
            // Manejar cualquier otra excepción que no sea de PDO
            echo "Error general: " . $e->getMessage();
        }
```

- Uso de Pipes Personalizado para para calcular los años segun una fecha
![img](/imgCanva/pipe.png)

# Futuras mejoras
- Pasar de SQL/PHP a Firebase
- Realizar mejoras en el diseño y en los estilos


# Demostración 
Enlace al video de demostración:
https://drive.google.com/file/d/1cciezox9TFSXOgsz4WXHDIZ53FrTf5yC/view?usp=sharing


## Algunas Utilidades y explicación 
### Importar iconos
Importar Iconos para su utilizacion en ionic y 
```javascript
import { IonIcon } from '@ionic/angular/standalone';
import { addIcons } from 'ionicons'; 
import { camera } from 'ionicons/icons'; //icono por icono

constructor() {
    addIcons({ camera });
  }
```


## Usar swiper
Swiper me ha permitido hacer el slider de las imagenes dentro de cada perfil de animal
https://ionicframework.com/docs/ja/v6/angular/slides


## Mapa leaflet

Lo he importado mediante CDN y usado mediante un componente propio para llamarlo

## Utilizar android
```bash
//Instalar utilidades de android para Ionic y angular
npm install @capacitor/core@5.7.0
npm install @capacitor/android

//Ejecutar compilador y creador de funciones de android
npx cap add android
ionic capacitor build android

// Ejecutar emulador y Android Studio
ionic capacitor sync android
npx cap run android

```
