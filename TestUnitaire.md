# Mockito
## @Mock
Est utilisée pour créer un objet fictif pour une classe particulière
## @InjectMocks
Est utilisée pour injecter l'objet fictif dans le Mock

Si il y a @InjectMocks alors il faut utiliser  @BeforeEach : 
```java
    @BeforeEach
    void setUp() {
        MockitoAnnotations.openMocks(this);
    }
```

## when()
- **Objectif :** utilisé pour stubbing ou Mocker un comportement particulier de la méthode.
- **Ce qu'il fait :** Permet de spécifier une valeur de retour ou une exception lorsqu'une méthode particulière est appelée avec certains arguments.
- **Quand l'utiliser :** 
  - Lorsque je dois Mocker un comportement spécifique ou le résultat d'un appel de méthode. (simuler un comportement)
  - Lorsque je ne veux pas savoir si une méthode est appelée ou non, mais que je veux contrôler sa sortie lorsqu'elle est appelée.

```java
when(mockedList.get(0)).thenReturn("firstElement");
```
### thenReturn()
Est utilisée pour spécifier ce que doit retourner un mock lorsque celle-ci est appelée.

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

## eq()
- La méthode eq() dans Mockito est utilisée pour matcher un argument exact dans les appels de méthode sur un mock.
- L'utilisation de eq() est une manière de spécifier que ces paramètres sont exactement ceux que j'ai defini dans le test.

### Pourquoi utiliser eq() ?
- Par défaut, Mockito essaie de faire correspondre les arguments d'un appel de méthode en fonction de leur type. Mais dans certains cas, cela peut ne pas être suffisant si vous voulez que l'argument soit exactement égal à un certain objet ou une valeur précise.
- eq() est utilisé pour s'assurer que les arguments qui sont passés au mock correspondent exactement à ceux que vous avez définis dans le test. Si vous n'utilisez pas eq(), Mockito pourrait tenter de faire une comparaison plus large qui ne vérifierait pas l'exactitude des valeurs. Cela pourrait entraîner des erreurs ou des tests qui ne reflètent pas la réalité du code.


## consumeWith()
- Permet d'afficher la réponse de expectBody()
```java
result.expectStatus().isOk()
              .expectBody()
              .consumeWith(response -> {
                  // Afficher le corps de la réponse dans la console
                  String responseBody = new String(response.getResponseBody());
                  System.out.println("Response Body: " + responseBody);
              });
```
²

## FAIRE ATTENTION : 
Si ```@WebFluxTest(controllers = nomducontroller.class)``` est présent alors ça ne sert à rien de @Mock le controller (TU non pris en compte par sonar)