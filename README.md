# ayudantia0410  
# Ayudantía 13/09
El mundo Pokémon es un universo ficticio lleno de criaturas llamadas Pokémon. Los entrenadores capturan, entrenan y se enfrentan en emocionantes batallas con sus Pokémon. Cada Pokémon tiene habilidades únicas y pertenece a uno o más tipos (como agua, fuego, eléctrico, etc.)

Este ejercicio se enfoca en el procesamiento de datos de Pokémon a partir de un archivo CSV llamado "pokemon.csv". Se proporcionan varias funciones para realizar diferentes tareas relacionadas con la información de Pokémon en el archivo. Aquí se encuentra una breve descripción de las funciones y cómo se utiliza el programa principal para completar varias tareas.

## Funciones
`leerPokemon(linea,pokedex)`: Esta función toma una línea de texto del archivo .csv que representa un Pokémon y su información. Analiza la línea y agrega información relevante sobre el Pokémon a la pokedex (diccionario). La información que se debe agregar es **nombre, tipo, total, vida, ataque, defensa**. Si el Pokémon es una mega evolución, se imprimirá un mensaje indicando que es una mega evolución. Retorna la pokedex actualizada. Un Pokémon que es mega evolución contiene la palabra "Mega" en su nombre.

Estructura del diccionario a retornar: 
```bash 
{"nombre pokemon" = {"tipo": tipo,"total": total,"vida": vida ,"ataque": ataque,"defensa": defensa}, "": {}, ...}
```

`encontrarTipos(pokedex)`: Esta función recorre la pokedex (diccionario) y devuelve una lista de todos los tipos de Pokémon únicos presentes en ella.

`burbuja(totales, nombres)`: Esta función implementa el algoritmo de ordenamiento **burbuja** para ordenar dos listas paralelas: una lista de valores totales y una lista de nombres. **Retorna las listas ordenadas (totales, nombres)**. El ordenamiento se basa en la lista "totales" que corresponden a numero enteros, los cambios que se hagan en esta lista para lograr ordenarla, deben hacerse tambien en la lista "nombres" para que así los nombres esten asociados a su valor correspondiente en la lista "totales".

Ejemplo:
```bash
[1, 4, 6, 3, 9 , 7], ["uno", "cuatro", "seis", "tres", "nueve", "siete"] -> [1, 3, 4, 6, 7, 9], ["uno", "tres", "cuatro", "seis", "siete", "nueve"]
```

`encontrarMasFuertes(pokedex,n)`: Esta función encuentra y muestra los N Pokémon más fuertes en términos de "total" (puntuación total). Primero, recopila los totales y nombres de todos los Pokémon en la pokedex, luego los ordena de mayor a menor y muestra los primeros N en la lista ordenada. **También los retorna (totales, nombre)**

`filtrarPorTipo(pokedex,tipo)`: Esta función filtra la pokedex para incluir solo Pokémon del tipo especificado y devuelve un nuevo diccionario con los Pokémon que cumplen con ese criterio.

## Estructura main
- Abre el archivo "pokemon.csv" en modo lectura y lee todas las líneas del archivo.
- Inicializa un diccionario pokedex vacío.
- Itera sobre cada línea en el archivo (excluyendo la primera línea que contiene encabezados) y llama a leerPokemon para - agregar la información del Pokémon a la pokedex.
- Utiliza la función encontrarTipos para obtener una lista de tipos de Pokémon únicos presentes en la pokedex.
- Para cada tipo de Pokémon encontrado:
- Llama a filtrarPorTipo para obtener un diccionario de Pokémon de ese tipo.
- Llama a encontrarMasFuertes para encontrar y mostrar los 10 Pokémon más fuertes de ese tipo.
- Crea un archivo de texto con el nombre del tipo y escribe los nombres y totales de los Pokémon más fuertes en ese archivo.
