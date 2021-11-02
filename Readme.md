## Проблема

Карта компонентов получается запутанной и непонятной

```mermaid
graph TD;

list-manager --> require-admin
get-apikey --> require-admin
get-apikey --> list-manager
current-user --> get-apikey
basic-desks-info --> list-manager
parking-deskpanel --> basic-desks-info
parking-deskpanel --> set-gray-deskpanel
booking-events --> basic-desks-info
check-bookable --> booking-events
check-bookable --> basic-desks-info
check-bookable --> set-gray-deskpanel
check-functions --> list-manager
check-functions --> current-user
check-functions --> booking-events
check-functions --> set-gray-deskpanel
booking-intersection --> list-manager
booking-intersection --> booking-events
simple-parking --> basic-desks-info
simple-parking --> booking-events 
simple-parking --> booking-intersection
simple-parking --> parking-deskpanel


```


## Задачи
1. Расположить компоненты по слоям, таким образом, что компоненты с меньшим числом зависимостей должны быть на более низких слоях чем компоненты с большим числом зависимостей. Соответсвенно компоненты от которых зависит меньшее число компонентов должны быть выше
2. Алгоритм минимального пересечения стрелок
3. Постараться учесть возможные циклические зависимости


```mermaid
graph TD;
subgraph Слой 1;
D
A
end
subgraph Слой 2;
B
end
subgraph Слой 3;
C
end
A --> C
A --> B
B --> C
D --> C
```




<!-- - require-admin
- list-manager
- get-apikey
- current-user
- basic-desks-info
- set-gray-deskpanel
- parking-deskpanel
- booking-events
- check-bookable
- check-functions
- booking-intersection
- simple-parking-->