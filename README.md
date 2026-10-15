# Grupo2.-Reto-Recorridos-recursivos-de-un-rbol-binario-de-b-squeda
Reto de recorridos recursivos de un árbol binario de búsqueda

Solución del reto de Estructura de Datos del paralelo SW-N3-A. Las matrículas se insertan en este orden:

```text
45, 25, 70, 10, 30, 60, 90, 27, 65
```

## Árbol resultante

```text
        45
       /  \
     25    70
    / \   /  \
  10  30 60  90
      /    \
     27    65
```

Cada matrícula menor que el nodo actual se inserta a su izquierda; cada matrícula mayor se inserta a su derecha. Las repetidas se ignoran.

## Recorridos

| Recorrido | Orden de visita | Resultado |
|---|---|---|
| Preorden | Nodo, izquierda, derecha | `45 25 10 30 27 70 60 65 90` |
| Inorden | Izquierda, nodo, derecha | `10 25 27 30 45 60 65 70 90` |
| Posorden | Izquierda, derecha, nodo | `10 27 30 25 65 60 90 70 45` |

Los tres métodos son recursivos. Cuando `nodo == null`, imprimen `null -> regresa` y terminan esa llamada. Al llegar a un nodo, imprimen `entra <matricula>`. El mensaje `VISITA <matricula>` y la adición a `salida` ocurren en la posición correspondiente a cada recorrido. La sangría aumenta dos espacios al llamar a cada hijo.
Código

La solución está en [`RetoRecorridos.java`](RetoRecorridos.java). Usa las clases `Estudiante` y `NodoEstudiante` que ya existen en el proyecto, dentro del paquete `reto`. El método `altura` devuelve la altura en aristas: `-1` para un árbol vacío y `0` para una hoja.

Para incorporarla al proyecto, coloca `RetoRecorridos.java` en el directorio del paquete `reto`, junto a las clases existentes. Ejecuta su método `main` para ver la traza y los resultados.

## Resultados esperados de las pruebas

| Caso | Preorden | Inorden | Posorden | Altura |
|---|---|---|---|---:|
| Reto SW-N3-A | `45 25 10 30 27 70 60 65 90` | `10 25 27 30 45 60 65 70 90` | `10 27 30 25 65 60 90 70 45` | 3 |
| Árbol vacío | Cadena vacía | Cadena vacía | Cadena vacía | -1 |
| Un nodo (`50`) | `50` | `50` | `50` | 0 |
| Cadena (`10, 20, 30, 40`) | `10 20 30 40` | `10 20 30 40` | `40 30 20 10` | 3 |
| Repetido (`20, 30, 30, 10`) | `20 10 30` | `10 20 30` | `10 30 20` | 1 |

En el último caso, la segunda matrícula `30` no se inserta. Si una salida no coincide, revisa en la traza dónde aparece `VISITA` respecto de las llamadas a los hijos.
