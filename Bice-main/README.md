# "Test de programación - Banco Bice Lab" propuesta de enfoque técnico

**Selected stack:**
  - Angular 11 / Bootstrap 
  - API Rest .Net Core 3.1 (C#)
  - URL servicio indicadores económicos
  
# Visión General

Se solicita construir una solución Web que se pueda conectar a la URL https://www.indecon.online/ con el obetivo de obtener uno o varios indicadores económicos.

**Solución resultante:**

<img src="Img/app1.png" width="80%"  />

**Contexto:**

- Como se puede apreciar, en las siguientes imágenes, la solución presenta un Front End inicial para listar Indicadores (en esta caso la búsqueda desencadenó un total de 10 tipos de ítemes). Los valores de fecha en el origen se encuentran en formato Unix Time (valor númerico) transformado al valor de fecha local. Tal como se muestra en la primera imagen se despliega la lista de ítemes con una paginación de 5 líneas por lista, y por último un resultado de búsqueda específica en la figura 3 y 4 por tipo de indicador.

<img src="Img/app_grid_page.png" width="75%"  />


- Búsqueda:
<img src="Img/app_grid_especific_result1.png" width="75%"  />


<img src="Img/app_grid_especific_result2.png" width="75%"  />


**NOTA: los valores de indicadores no son rodonadeados, se muestran con tipo de unidad respectivo.**

- Además, se detalla búsqueda errónea para ingreso de números y símbolos.

<img src="Img/app_grid_especific_result_error.png" width="75%"  />


# Aspectos destacados del esquema y la arquitectura de la solución técnica

- Primero tendremos tres partes principales acopladas como se mencionó al principio, implementadas y ejecutándose en una máquina local, e interactúan de acuerdo con la siguiente imagen:

<img src="Img/solution_components_arqt.png" width="80%"  />


- En segundo lugar, con respecto al componente "frontal" (aplicación Angular 11), a continuación se muestra la estructura simple de los componentes:

<img src="Img/angular_arrange.png" width="80%"  />


- Una API REST construida en .NET Core 3.1 tiene una arquitectura interna de N-Layer para asegurar la separación de responsabilidades y la mantenibilidad que sigue el enfoque del siguiente diagrama:

<img src="Img/api_approach.png" width="80%"  />


- Árbol de solución API REST:

<img src="Img/solution_tree.png" />


- Finalmente el resultado de un test de la API REST construida en .NET Core 3.1 MsTest tal como se aprecia en el árbol de solución.

<img src="Img/solution_test.png" />
Fig.10

# Despliegue solución Angular

- Una vez compilado nuestro proyecto se debe ejecutar el siguiente comando Angular CLI en el diretorio raíz de este último: ..\ng build --prod

<img src="Img/app_ng_serve_open.png" />
Fig.11

<img src="Img/app_ng_build_prod.png" />
Fig.12

- Luego de este proceso se genera una carpeta llamada 'dist' que contiene todos los archivos que debemos subir a nuestro servidor de desplieque (producción) internet:

<img src="Img/app_ng_dist.png" />
Fig.13

# Despliegue solución API REST

- Para nuestro proyecto API REST se debe ejecutar la opción de Publicación de VS Net Core para generar los archivos del Release (Kit de implementación) para subir en el servidor de de desplieque (producción) internet. 

<img src="Img/api_publish1.png" />
Fig.14

<img src="Img/api_publish2.png" />
Fig.15

- Luego de generar el Release se debe crear un Directorio Virtual en el IIS del servidor de despliegue con el Aplication Pool respectivo. Copiar el Kit de imlementación en el directorio recién creado en el IIS.
