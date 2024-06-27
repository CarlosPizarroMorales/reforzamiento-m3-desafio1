# Desafío Blog FrontEnd I

## Descripción general

El mismo cliente de ejercicios anteriores ha solicitado realizar un rediseño de la página principal de su blog aplicando la metodología [BEM][11]. Además, ha sugerido que el proyecto se realice utilizando solamente CSS Flexbox. Nos ha entregado una [maqueta][10] para orientarnos con la vista final:


![maqueta][13]


## Guía de estilos:

- Tipografía:
  - Poppins 400
  - Poppins 500
  - Poppins 700
- Colores:
  - #000000
  - #e93e30
  - #f7e018
  - #299ed5 
  - #292c33 
  - #67c770
  - #563d7c

## Requerimientos:

1. **1 pt.** Crear la estructura de carpeta solicitada:
```
/assets/css/style.css
/assets/img/logos
/assets/img/posts

```
2. **2 pts.** Utilizar elementos semánticos para definir las secciones de la página
3. **2 pts.** Utilizar sintaxis BEM para nombres de clases.
4. **1 pt.** Utilizar la fuente Poppins con sus pesos y tamaños.
5. **2 pts** Crear bloques reutilizables para las cards y categorías.
6. **2 pts** Utilizar modificadores para la sección de categorías
7. **Opcional** Crear versión responsive de la página.

## Recursos:

- Maqueta en [Figma][10]
- Documentación oficial [BEM][11]
- Fuente Poppins en [Google Fonts][12]
- Convención de [naming][14] para BEM

## Análisis: 

### Estilos

1. El viewport es de 1280px. 
2. El body utiliza un width de ~82% (~110 padding/lado)
3. Se obsevan dos componentes comunes: 
   1. El logo Desafío Latam
   2. El "usuario"
   3. La card con variación horizontal
   4. Los tags
4. Tipografía:
   1. 700/24 texto en logo
   2. 700/28 texto en títulos de sección
   3. 700/24 texto en títulos main card
   4. 700/20 texto en títulos de otras cards
   5. 500/24 texto en usuario en main card
   6. 500/16 texto en usuario en otras cards
   7. 400/18 texto fecha en main card
   8. 400/16 texto fechas en otras cards
   9. 400/20 texto enlace ver todas las categorías
   10. 400/20 texto footer

### Layout

1. Se considerarán las siguientes grandes secciones: 
   1. nav **bloque** `.navbar`
   2. main **bloque** `.main` para todo el contenido en novedades + populares
   3. footer **bloque** `.footer`  ( _¿por qué?_ consistencia metodológica y curva de especificidad)
2. Dentro de `.navbar` y `.footer`: 
   1. El componente será el **bloque** `.logo`.
   2. Además el footer tendrá un **bloque** `.copyright`. 
3. Dentro de `.main` distinguiremos 2 secciones con 2 secciones cada una a su vez:
   1. `section.novedades-container` que contiene 2 wrappers: uno para el bloque `.card .card--main` y luego otro wrapper con la sección de card horizontales `.card .card--horizontal`
   2. La segunda parte también tiene 2 wrappers, esta vez cada uno es una sección en sí mismo siendo el wrapper general un `div.populares-container` para insertar el `section.populares` que tiene 4 componentes `.card` y luego otra `section.tags` con 6 componentes de bloque `tag`.

### Anatomía BEM de los componentes: 

#### Componente card
- `.card`
  - `.card__img`
  - `.card__date`
  - `.card__title`
  - `.user` (componente, ver [abajo][15])
  
#### Componente logo
- `logo`
  - `logo__img`
  - `logo__brand`

#### Componente user
- `.user`
  - `.user__avatar`
  - `.user__name`

#### Componente tag
- `.tag`
  - `.tag__img`
  - `.tag__name`

#### Componente copyright
- `.copyright`
  - `.copyright__brand`
  - `.copyright__year`

#### Otras clases útiles: 
- `.heading` para los 3 encabezados
- `.link-more` para el link "Ver todas las categorías"

<!-- Enlaces del documento -->
[10]:https://www.figma.com/design/adUnzFLoVoDlhv61kvJNjN/Blog-FrontEnd?node-id=0-1&t=7B3ROffrC97mMXSR-0
[11]:https://en.bem.info
[12]:https://fonts.google.com/selection?query=poppins
[13]:./assets/util/maqueta.png
[14]:https://en.bem.info/methodology/naming-convention/#alternative-naming-schemes
[15]:#componente-user