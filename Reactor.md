# Reactor
## Publisher
Un Publisher est un fournisseur d'un nombre potentiellement illimité d'éléments séquencés, les publiant en fonction de la demande reçue de son subscriber.


## Flux
Retourn un flux de données asynchrone sur lequel plusieurs filtres son applicable 
ex :
```java
Flux()
```

### Function
- flatMap
Transform l'element emis par un flux en Publishers, puis le transforme en single Flux