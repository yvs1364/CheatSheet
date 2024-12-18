# Mockito

## when()
- **Objectif :** utilisé pour stubbing ou Mocker un comportement particulier de la méthode.
- **Ce qu'il fait :** Permet de spécifier une valeur de retour ou une exception lorsqu'une méthode particulière est appelée avec certains arguments.
- **Quand l'utiliser :** 
  - Lorsque je dois Mocker un comportement spécifique ou le résultat d'un appel de méthode. (simuler un comportement)
  - Lorsque je ne veux pas savoir si une méthode est appelée ou non, mais que je veux contrôler sa sortie lorsqu'elle est appelée.

```java
when(mockedList.get(0)).thenReturn("firstElement");
```

## verify()
- **Objectif :** utilisé pour la vérification des appels de méthode sur des objets fictifs.
- **Ce qu'il fait :** Il vérifie qu'une certaine méthode a été appelée avec certains arguments.

- **Quand l'utiliser :**
  - Pour s'assurer qu’une méthode spécifique a été appelée sur l’objet fictif.
  - Pour également s'assurer qu'une méthode spécifique a été appelée un certain nombre de fois ou avec certains arguments.
```java
mockedList.add("one");
verify(mockedList).add("one");
```
