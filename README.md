# Dolores AR

Aplicación de Flutter sobre lugares turísticos de Dolores Hidalgo usando realidad aumentada.

La app permite:

- Ver lugares cercanos.
- Calcular distancia y dirección.
- Mostrar etiquetas sobre la cámara.
- Guardar sellos en un pasaporte turístico.
- Usar un modo de demostración.

## Captura de la aplicación

![Pantalla de Dolores AR](capturas/24-pantalla-inicio-app.png)

## Cómo ejecutarlo

```bash
flutter pub get
flutter run
```

## Pruebas

Primero hice una ejecución con una función faltante para mostrar la fase roja. Después quité esa prueba temporal y ejecuté todas las pruebas del proyecto.

```bash
flutter test
```

| Prueba con error | Pruebas terminadas |
|---|---|
| ![Error real en la terminal de VS Code](capturas/tdd_rojo_error.png) | ![Pruebas aprobadas en la terminal de VS Code](capturas/pruebas_vscode.png) |

Resultado final: **42 pruebas aprobadas**.
