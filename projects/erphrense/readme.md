# Erphrense

### Automatisation des tests

Afin d'automatiser les tests, nous devons les écrire ! Je vous invite donc à écrire les tests unitaires dans l'ordre bottom-up :

1. Tests unitaire de TicketProvider
2. Tests unitaire de JetProvider
3. Tests unitaire de BookingService
4. Tests unitaire de BookingController

ATTENTION : A l'heure actuelle, BookingController est couplé avec BookingService. Il faudra les désolidariser en ajoutant une interface pour introduire de l'abstraction et pouvoir tester unitairement la classe BookingController.

### Pour aller plus loin

Pour Java, il est possible d'utiliser Mokito qui vous permet de mocker facilement les interfaces. Pour ajouter Mokito à votre application Java :

```xml
<dependency>
    <groupId>org.mockito</groupId>
    <artifactId>mockito-core</artifactId>
    <version>2.21.0</version>
</dependency>
```

Ensuite vous pouvez définir vos mocks de la macnière suivante :

```java
BookingServiceTest.ticketProvider = mock(CancelableProvider.class);
when(BookingServiceTest.ticketProvider.cancel(0)).thenReturn(true);
```