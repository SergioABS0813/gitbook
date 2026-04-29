# Los 4 principios de diseño

Abstracción: Es la información más relevante de un objeto en un determinado contexto.

{% hint style="info" %}
Ejemplo práctico: No es lo mismo un "Usuario" en un software de venta de ropas que en un software de una clínica. Hay detalles que son más relevantes dado un contexto.
{% endhint %}

Encapsulación: Empaqueta datos y métodos que operan sobre esos datos en una sola unidad (clase). Busca dos objetivos principales: RESTRINGIR acceso directo a los componentes internos y EXPONER solo lo necesario públicamente.

{% hint style="info" %}
Ejemplo práctico: El encapsulamiento permite tener la data abstraída como el comportamiento de la clase en una misma unidad (clase).
{% endhint %}

Descomposición: Es tomar un todo y descomponerlo en pequeñas partes o tomar varias partes con diferentes funcionalidades y combinarlas, convirtiéndolas en un todo.

{% hint style="info" %}
Ejemplo práctico: Observas un carro y te das cuenta que este se compone de diferentes partes y estas, en conjunto, hacen el carro. Además si tomas una de esas partes, te das cuenta que también se puede descomponer en más partes pequeñas.
{% endhint %}

Generalización: Ayuda a reducir la redundancia de información. Esto se traduce a tener una SUPERCLASE del cual tenga CLASES HIJAS para que puedan heredar atributos y comportamientos (métodos). Ayuda a que sea más reutilizable el código y se puedan hacer cambios de manera más general que clase por clase.

{% hint style="info" %}
Ejemplo práctico: SUPERCLASE Animal la cual tiene atributos y comportamientos que heredan las clases PERRO y GATO.
{% endhint %}



