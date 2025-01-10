# Reactor
## Publisher
Un Publisher est un fournisseur d'un nombre potentiellement illimité d'éléments séquencés, les publiant en fonction de la demande reçue de son subscriber.



## Mono

### Function
- zip
Mono.zip prend plusieurs Mono et les combine en un seul Mono qui émet un tuple (Tuple2, Tuple3, etc.) contenant les résultats de ces Mono. Chaque Mono est exécuté indépendamment et une fois que tous les Mono sont résolus, le tuple est émis.





## Flux
Retourn un flux de données asynchrone sur lequel plusieurs filtres son applicable 
ex :
```java
Flux()
```

### Function
- flatMap
Transform l'element emis par un flux en Publishers, puis le transforme en single Flux
- collectList
Collecte tous les éléments émis par le Flux dans une liste qui est émise par le Mono résultant lorsque cette séquence est terminée, émettant la liste vide si la séquence était vide.
- switchIfEmpty :
Permet de gérer le cas où le flux est vide en fournissant un flux alternatif, ce qui rend votre code plus fonctionnel en utilisant des opérations réactives sans avoir besoin de faire de vérifications manuelles comme un if.