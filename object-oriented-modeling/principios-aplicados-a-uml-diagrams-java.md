# Principios aplicados a UML Diagrams Java

### Abstracción aplicada en Diagrama de clase

CRC Cards sirven para un diseño de concepto del software, pero para la implementación se emplea Diagramas de Clase UML o DIagrama de Clase (Class Diagram).

Los Diagramas de Clase se traducen fácilmente en código. Se componen en 3 partes: Nombre de la clase, Atributos (nombre y tipo de dato) y Métodos (Funciones que harán los objetos dentro de la clase).

<figure><img src="../.gitbook/assets/2016-01-08-uml-img2.png" alt=""><figcaption></figcaption></figure>

### Encapsulación aplicada en Diagrama de clase

Se coloca signo "-" para denotar que el atributo es privado y "+" si es público.

{% hint style="info" icon="book-open-lines" %}
Se accede únicamente a los atributos privados desde la propia clase. Para poder controlar se usan métodos públicos (Get y Set) para poder manipular estos atributos, al colocarlos, tenemos más control sobre cuándo y cómo se manipulan los datos dentro de un objeto.
{% endhint %}

<figure><img src="../.gitbook/assets/encapsulacion_diagrama_uml.png" alt="" width="375"><figcaption></figcaption></figure>

Getters: Métodos que permiten retornar información acerca de una clase.

Setters: Métodos que permiten colocar o cambiar información (en un atributo privado) de forma segura y protegida.

### Descomposición aplicada en Diagrama de clase

Relación débil (Aggregation): Cuando existe una relación en la que una entidad puede existir sin otra entidad.

{% hint style="success" %}
Ejemplo práctico: La clase Aereolínea puede tener o no Pasajeros. No por que no tenga significa que no exista la Aerolínea.
{% endhint %}

```java
public class PetStore {
    private ArrayList<Pet> listPets;
    
    public PetStore(){ //Constructor
        this.listPets = new ArrayList<Pet>();
    }
    
    public void add(Pet pet){
         //logic
    }

}
```

Relación fuerte (Composition): Cuando existe una relación en la que una entidad no puede existir sin otra entidad.

{% hint style="success" %}
Ejemplo práctico: Una habitación dentro de una Casa, si quitamos la Casa, entonces esa habitación ya no existiría.
{% endhint %}

```java
// Relación fuerte, sin salario, no hay Empleado
public class Employee{
    private Float salary;
    
    public Employee(Float salary){
        this.salary = salary;
    }

}
```

### Herencia aplicado a Diagrama de clase

En el diagrama se denota como superclase (clase padre), las clases que están más arriba, como si se tratase de un árbol genealógico.

<figure><img src="../.gitbook/assets/Screenshot 2026-04-29 234121.png" alt="" width="254"><figcaption></figcaption></figure>

{% hint style="success" %}
Ejemplo práctico: Superclase Animal y Subclase Perro.

<p align="center"><img src="../.gitbook/assets/Screenshot 2026-04-29 234511.png" alt="" data-size="original"></p>

En este diagrama, no se colocan los atributos ni métodos de la clase Animal en la clase Dog, ya que se sobreentiende que las hereda ya que Dog es subclase de Animal.
{% endhint %}

{% hint style="info" icon="book-open-lines" %}
Importante: En Java un Protected attribute o método solo puede ser accedido por:

* Misma clase encapsuladora
* Todas las subclases
* Todas las clases que están en el mismo package
{% endhint %}

{% hint style="info" icon="book-open-lines" %}
En Java, Package es un lugar en donde se ordenan las clases.
{% endhint %}

{% hint style="info" icon="book-open-lines" %}
Importante: Cuando se coloca la palabra clave  "abstract", se declara a Java que esa clase no se podrá instanciar.

<p align="center"><img src="../.gitbook/assets/Screenshot 2026-04-29 235633.png" alt="" data-size="original"></p>

En este caso, la clase Animal, no se podrá instanciar en objetos.
{% endhint %}

{% hint style="success" %}
Ejemplo práctico: En código, la clase Dog hereda de la clase Animal. Se usa "extends" y el nombre de la clase Animal

<p align="center"><img src="../.gitbook/assets/Screenshot 2026-04-29 235927.png" alt="" data-size="original"></p>
{% endhint %}

{% hint style="info" icon="book-open-lines" %}
**Constructores**

Hay 2 tipos de constructores:

* Implícito: No se escribe en el código.
* Explícito: Se escriben en el código. Sirven para asignar valores a los atributos en el momento de la instanciación.
{% endhint %}

```java
public abstract class Animal {
    protected int numberOfLegs;
    
    public Animal (int legs){
        this.numberOfLegs = legs;
    }
}
```

```java
public class Dog extends Animal{
    public Dog(int legs){
        super(legs)
    }
}
```

Se puede hacer una sobreescritura en los métodos de la clase Padre dentro de la clase Hijo, simplemente se coloca el mismo nombre del método de la clase Padre y con la lógica que se quiere que se aplique dentro de la clase Hijo.

```java
public abstract class Animal {
    protected int numberOfLegs;
    public void saludar(){
        System.out.println("Hola, soy un animal");
    }
}
```

```java
public class Dog extends Animal{
    public Dog(int legs){
        super(legs);
    }
    public void saludar(){
        super.saludar(); //Se ejecuta el método de la clase Padre
        System.out.println("soy un perro");
    }
}
```

### Generalización aplicada en Diagrama de clase

{% hint style="info" icon="book-open-lines" %}
Una interfaz de Java solo contiene la firma de los métodos (nombre del método y los tipos de datos de los argumentos).

* Interfaz en Java no es una clase.
* Se usa para definir métodos (comportamientos) que van a compartir múltiples clases.
{% endhint %}

{% hint style="success" %}
Ejemplo práctico: **Firma de un método**

`public void arreglarCarro(String action, Time time)`&#x20;

Firma:

* arreglarCarro(String, Time)
{% endhint %}

