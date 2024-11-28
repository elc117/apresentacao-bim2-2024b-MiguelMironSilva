# HashMaps em Java

 - Discente: Miguel Miron Silva
 - Docente: Andrea Schwerter Charão
 - Disciplina: Paradigmas de Programação

---

## Sobre HashMaps

<p>A classe <b>HashMap</b> é parte do pacote `java.util` e uma implementação da interface `Map`, sendo utilizado para criar <i>pares ordenados</i> de dados, que podem ser referenciados de acordo com cada membro no par depois </p>
<p>A técnica de <i>Hashing</i>  utilizada nele converte strings grandes em strings menores, facilitando sua busca.</p>
<p>Esses pares ordenados têm a forma de dados armazenados, na sua forma genérica, em pares `key` e `value`. Cada chave é associada à um certo valor, e pode-se acessar valores usando suas respectivas chaves.</p>
<p>Os pares são ordenados pela ordem de suas <i>hashes</i>, sendo essencialmente ordenados aleatoriamente, em contraste com estruturas como `TreeMap`.</p>

### Características de HashMaps

<p><b>Pares de chaves e valores:</b> Cada elemento no HashMap consiste em uma chave e um valor, com a chave sendo usada para procurar o valor associado.</p>

<p><b>Tempo de acesso rápido:</b> Inserção e remoção de elementos tem complexidade de tempo O(1) e complexidade de espaço O(N).</p>

<p><b>Função de Hashing:</b> A utilização de funções de hash para mapear chaves em um índice dentro de um arrray resulta em uma busca rápida de valores, baseado em chaves.</p>

<p><b>Suporte à chaves e valores nulos:</b> Chaves nulas podem ser usadas para armazenar valores, e valores podem estar associados à chaves nulas.</p>

<p><b>Desordenado:</b> A ordem em que os elementos são inseridos no HashMap não é preservada.</p>

<p><b>Valores duplicados:</b> O HashMap permite valores duplicados, mas nunca chaves - se uma chave duplicada é inserida, o valor que a chave original tinha é sobrescrito.</p>
<p> - A estrutura `LinkedHashMap` preserva a ordem de inserção.</p>

<p><b>Não seguro para threads:</b> Se múltiplas threads acessarem o mesmo valor em um HashMap simultaneamente, isso pode levar à inconsistências de dados.</p>
<p> - Se é necessária a segurança para acesso em threads, pode-se usar a estrutura `ConcurrentHashMap`.</p>

<p><b>Capacidade e fator de carga:</b> HashMaps têm uma capacidade, que é o número de elementos que ele pode conter, e um fator de carga, que é a medida de quão cheio o hashmap pode estar antes de ser redimensionado.</p>
<p> - A carga padrão é 16 e o fator de carga padrão é 0.75</p>

---

## Construção de HashMaps

### Sintaxe
<p>Para utilizarem-se HashMaps, deve-se importar o pacote `java.util` primeiro</p>

```
import java.util.HashMap
````

<p>Após isso, pode-se criar uma classe HashMap: </p>

```
HashMap<KeyDataType, ValueDataType> myHashMap = new HashMap<KeyDataType, ValueDataType>();
```

---

## Exemplos de Uso

### Acesso à itens
```java

import java.util.HashMap;

public class Main {
  public static void main(String[] args) {
    HashMap<String, String> cursoProfessor = new HashMap<String, String>();

    // Adiciona-se chaves e valores (CursoNome, Professor)
    cursoProfessor.put("História", "Bernardo");
    cursoProfessor.put("Matemática", "Ana");
    cursoProfessor.put("Física", "Maria");

    System.out.println(cursoProfessor.get("Física"));
    System.out.println(cursoProfessor.get("História"));
  }
}

```

<p>A output será:</p>

```
Maria
Ana
```

### Adição de itens

```java

import java.util.HashMap;

public class Main {
  public static void main(String[] args) {
    HashMap<String, String> cursoProfessor = new HashMap<String, String>();

    cursoProfessor.put("História", "Bernardo");
    cursoProfessor.put("Matemática", "Ana");
    cursoProfessor.put("Física", "Maria");

    System.out.println(cursoProfessor);
  }
}

```

<p>A output será:</p>

```
{História=Ben, Matemática=Ana, Física=Maria}
```

### Remoção de itens

<p>Para se remover um item em particular: </p>

```java

import java.util.HashMap;

public class Main {
  public static void main(String[] args) {
    HashMap<String, String> cursoProfessor = new HashMap<String, String>();

    cursoProfessor.put("História", "Bernardo");
    cursoProfessor.put("Matemática", "Ana");
    cursoProfessor.put("Física", "Maria");

    cursoProfessor.remove("Physics");
    System.out.println(cursoProfessor);
  }
}

```

<p>A output será:</p>

```
{História=Ben, Matemática=Ana}
```

<p>Para se remover todos os itens: </p>

```java

import java.util.HashMap;

public class Main {
  public static void main(String[] args) {
    HashMap<String, String> cursoProfessor = new HashMap<String, String>();

    cursoProfessor.put("História", "Bernardo");
    cursoProfessor.put("Matemática", "Ana");
    cursoProfessor.put("Física", "Maria");

    cursoProfessor.clear();
    System.out.println(cursoProfessor);
  }
}

```

<p>A output será:</p>

```
{}
```

### Navegando um HashMap

<p>Navvegando utilizando-se de .keySet(): </p>


```java

public class Main {
  public static void main(String[] args) {
    HashMap<String, String> cursoProfessor = new HashMap<String, String>();

    cursoProfessor.put("História", "Bernardo");
    cursoProfessor.put("Matemática", "Ana");
    cursoProfessor.put("Física", "Maria");

    System.out.println("Cursos oferecidos:");

    for (String i : professorCurso.keySet()) {
      System.out.println(i);
    }

    System.out.println("\n Professores:");

    for (String i : cursoProfessor.values()) {
      System.out.println(i);
    }
  }
}

```

<p>A output será:</p>

```
Cursos:
Matemática
História
Física

Professores:
Ana
Bernardo
Maria
```

<p>Navvegando utilizando-se de .entrySet(): </p>


```java

import java.util.*;

public class Main {
  public static void main(String[] args) {
    HashMap<String, String> cursoProfessor = new HashMap<String, String>();

    cursoProfessor.put("História", "Bernardo");
    cursoProfessor.put("Matemática", "Ana");
    cursoProfessor.put("Física", "Maria");


    for (Map.Entry<String, String> entry: cursoProfessor.entrySet()) {
      System.out.printf("Curso: %s",entry.getKey());
      System.out.printf("Professor: %s \n", entry.getValue());
    }

  }
}

```

<p>A output será:</p>

```
Curso: Matemática Professor: Ana
Curso: História Professor: Bernardo
Curso: Física Professor: Maria
```

---

## Bibliografia

 - HashMap in Java: (https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)
 - Map and HashMap in Java: (https://www.youtube.com/watch?v=H62Jfv1DJlU)
 - Java | HashMap: (https://www.codecademy.com/resources/docs/java/hashmap)
 - HashMap (Java Platform SE 8): https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html
