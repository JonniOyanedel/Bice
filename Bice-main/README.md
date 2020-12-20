# "Test de programación - Banco Bice Lab" propuesta de enfoque técnico

**Selected stack:**
  - Angular 11 / Bootstrap 
  - API Rest .Net Core 3.1 (C#)
  - URL servicio indicadores económicos
  
# Visión General

Se solicita construir una solución Web que se pueda conectar a la URL https://www.indecon.online/ con el obetivo de obtener uno o varios indicadores económicos.

**Solución resultante:**

<img src="Img/app.png" width="80%"  />

<img src="Img/app_grid.png" width="80%"  />

...Como se puede apreciar, en las siguientes imágenes, la solución presenta un Front End inicial para listar Indicadores (en esta caso la búsqueda desencadenó un total de 10 tipos de ítemes). Los valores de fecha en el origen se encuentran en formato Unix Time (valor númerico) transformado al valor de fecha local. Tal como se muestra en la primera imagen se despliega la lista de ítemes con una paginación de 5 líneas por lista, y por último un resultado de búsqueda específica en la segunda y tercera imagen por tipo de inidcador.

<img src="Img/app_grid_page.png" width="75%"  /> 
<img src="Img/app_grid_especific_result1.png" width="75%"  /> 
<img src="Img/app_grid_especific_result2.png" width="75%"  />

**NOTA: los valores de indicadores no son rodonadeados, se muestran con tipo de unidad respectivo.**

- Además, se detalla búsqueda errónea para ingreso de números y símbolos.

# Aspectos destacados del esquema y la arquitectura de la solución técnica

- Primero tendremos tres partes principales acopladas como se mencionó al principio, implementadas y ejecutándose en una máquina local, e interactúan de acuerdo con la siguiente imagen::

<img src="Img/solution_components.jpg" width="80%"  />

- En segundo lugar, con respecto al componente "frontal" (aplicación Angular 11), a continuación se muestra la estructura simple de los componentes:

<img src="Img/angular_arrange.png" width="80%"  />

- Una API REST construida en .NET Core 3.1 tiene una arquitectura interna de N-Layer para asegurar la separación de responsabilidades y la mantenibilidad que sigue el enfoque del siguiente diagrama:

<img src="Img/api_approach.png" width="80%"  />

<img src="Img/solution_tree.png" />

- Finalmente el resultado de un test de la API REST construida en .NET Core 3.1 MsTest tal como se aprecia en el árbol de solución.

<img src="Img/solution_test.png" /> 