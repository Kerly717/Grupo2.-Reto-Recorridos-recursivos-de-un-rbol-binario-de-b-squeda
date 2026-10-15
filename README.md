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
