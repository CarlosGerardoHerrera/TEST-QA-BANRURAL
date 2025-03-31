# Estrategia de Pruebas

## Error 1: Generación del número aleatorio incorrecta
**Descripción:**  
El número aleatorio se estaba generando con `Math.random() * 10`, lo que provocaba que se obtuvieran valores decimales y no cubría el rango de 1 a 100.  
**Solución:**  
Se corrigió el código para generar un número entero entre 1 y 100 de manera correcta utilizando `Math.floor(Math.random() * 100) + 1;`.

---

## Error 2: Falta de validación de los números ingresados
**Descripción:**  
El juego no verificaba si el número ingresado por el jugador era realmente un número entero entre 1 y 100. Esto permitía que el jugador ingresara valores no válidos.  
**Solución:**  
Se añadió una validación para comprobar que el número ingresado sea válido. Si no es un número entero, se muestra una alerta y no se cuentan los intentos.

---

## Error 3: Colores incorrectos en los mensajes de resultado
**Descripción:**  
El color de los mensajes de resultado no era el adecuado. El mensaje de derrota aparecía con un fondo negro, y el mensaje de victoria no era claro.  
**Solución:**  
Se ajustaron los colores para que el mensaje de victoria sea verde y el de derrota sea rojo, tal como se indicó en los requisitos del juego.

---

## Error 4: Lógica incorrecta de los intentos
**Descripción:**  
El juego no estaba controlando correctamente el número de intentos. No se mostraba el mensaje adecuado cuando el jugador no adivinaba el número en los 10 intentos.  
**Solución:**  
Se corrigió la lógica para asegurarse de que el jugador tuviera un máximo de 10 intentos. Si el jugador no adivinaba el número en ese tiempo, se muestra el mensaje correspondiente.

---

## Error 5: Comparación incorrecta de los valores ingresados
**Descripción:**  
La comparación `if(userGuess === randomNumber)` no funcionaba correctamente porque `userGuess` es un string y `randomNumber` es un número.  
**Solución:**  
Se añadió `parseInt()` para convertir `userGuess` a un número antes de compararlo con `randomNumber`. De esta forma, la comparación es correcta.

---

## Error 6: Color de mensaje incorrecto cuando el jugador pierde
**Descripción:**  
El código original usaba `lastResult.style.backgroundColor = 'black';` cuando el jugador perdía, pero el color correcto para el mensaje de derrota debía ser rojo.  
**Solución:**  
Se corrigió el color del mensaje de derrota a rojo utilizando `lastResult.style.color = 'red';`.

---

## Error 7: Mensaje incorrecto cuando el jugador gana
**Descripción:**  
El mensaje que aparece cuando el jugador gana estaba mal escrito y no era claro. Decía `!!!Pérdistes!!!`, lo cual no era adecuado.  
**Solución:**  
Se cambió el mensaje a algo más adecuado y claro: `'Felicitaciones! adivinaste el número!'`.

---

## Error 8: Errores en la asignación de los `eventListener`
**Descripción:**  
En los `eventListener` había un error tipográfico. Se estaba utilizando `addeventListener` en lugar de `addEventListener`, lo que causaba que no funcionaran correctamente.  
**Solución:**  
Se corrigió la escritura de los `eventListener` para que funcionaran correctamente:
```javascript
guessSubmit.addEventListener('click', checkGuess);
resetButton.addEventListener('click', resetGame);
 
---

## Error 9: Generación incorrecta de un nuevo número aleatorio al reiniciar el juego

**Descripción:**  
Al reiniciar el juego, la generación del número aleatorio no estaba funcionando correctamente. El código `Math.floor(Math.random()) + 1` siempre devolvía 1, ya que `Math.random()` genera un valor decimal entre 0 y 1, y al usar `Math.floor()`, se redondeaba a 0.

**Solución:**  
Se corrigió el código para generar un número aleatorio válido entre 1 y 100 utilizando:  
```javascript
randomNumber = Math.floor(Math.random() * 100) + 1;