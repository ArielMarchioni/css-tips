# ¿Por qué usamos `::before`, `mask` y `mask-composite`?

En este ejemplo, se utiliza una combinación de `::before`, `mask` y `mask-composite` para crear un efecto visual atractivo alrededor del botón. Aquí explicamos por qué se usan estas propiedades:

## 1. Uso de `::before`

El pseudo-elemento `::before` es clave para añadir estilos adicionales sin modificar directamente el HTML. En este caso:

- **Razón principal**: Crear un contenedor visual que actúe como "borde" decorativo alrededor del botón.
- **Ventaja**: Separar los estilos visuales del contenido del botón, manteniendo el diseño modular y flexible.
- **Cómo funciona**: Al posicionar `::before` con `position: absolute` e igualar sus dimensiones al contenedor (`inset: 0`), se asegura que ocupe todo el área del botón.

## 2. Uso de `mask`

La propiedad `mask` define áreas visibles y ocultas del pseudo-elemento basado en patrones. En este caso:

- **Razón principal**: Permitir que solo el borde del gradiente sea visible, mientras el interior permanece transparente.
- **Cómo funciona**: 
  - **`linear-gradient(#000 0 0) content-box`**: Define la máscara exterior basada en el contorno del contenido del botón.
  - **`linear-gradient(#000 0 0)`**: Controla qué partes del gradiente se muestran.

## 3. Uso de `mask-composite`

La propiedad `mask-composite` controla cómo se combinan las diferentes máscaras aplicadas al pseudo-elemento.

- **Razón principal**: Especificar que las áreas superpuestas entre las máscaras deben excluirse (`exclude`), creando un efecto "recortado".
- **Cómo funciona**: 
  - **`exclude`**: Las máscaras se restan entre sí, dejando visibles solo las áreas deseadas (en este caso, el "borde").

## ¿Por qué esta combinación?

El uso de estas propiedades juntas permite lograr un efecto decorativo moderno que sería difícil de conseguir con bordes tradicionales. Además:

- Es más flexible y personalizable, ya que el gradiente y las máscaras pueden ajustarse fácilmente.
- Permite mantener un diseño limpio y separado, dejando el contenido del botón libre de estilos adicionales.

Este enfoque es ideal para interfaces modernas que buscan destacar visualmente con un diseño minimalista y funcional.
