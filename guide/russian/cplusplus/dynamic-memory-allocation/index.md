---
title: Dynamic Memory Allocation
localeTitle: Динамическое распределение памяти
---
## Распределение динамической памяти в C ++

### Что такое динамическое распределение памяти на C ++?

*   **Распределение памяти** в C ++ относится к памяти, выделенной для переменных, которые вы используете в своей программе.
*   **Динамическое распределение памяти** - это память, которая привязана к переменным во время выполнения, и объем требуемой памяти также определяется во время выполнения.
*   Эта память исходит из **кучи** , тогда как _нестатические_ переменные и _локальные_ переменные получают память из **стека** .
*   В C ++ программист может выполнять выделение памяти вручную и называется распределением **_динамической памяти_** .
*   В C можно было выполнять динамическое распределение памяти, используя функции _calloc_ и _malloc_ для выделения памяти и использования _свободной_ функции для де-распределения динамической памяти.
*   В C ++ в дополнение к выше, есть две функции: _новые_ и _удаленные_ для выполнения динамического распределения памяти и де-распределения.

### Оператор NEW

*   `new` оператор может предоставить память программиста из кучи (если доступно). Если память, запрошенная программистом, доступна, то `new` оператор инициализирует память, а затем возвращает адрес (ссылку) выделенной памяти.
*   **Синтаксис**  
    `pointer-variable-type` = **новый** `data-type;`  
    Пример 1: `int *ptr` = **new** `int;`  
    Пример 2: `int *ptr2` = **новый** `int[10];`  
    Здесь `pointer-variable-type` является **указателем** типа `data type` . Тип `data-type` может быть int, char и т. Д. Или определяемым пользователем типом данных.

### Оператор DELETE

*   Ответственность программиста заключается в том, чтобы де-распределить динамически выделенную память, иначе память не будет доступна для перераспределения до конца программы.
    
*   Чтобы освободить память, оператор `delete` доступен и может быть использован программистом.
    
*   **Синтаксис**  
    **удалить** `pointer-type-variable;`  
    Например, чтобы освободить память, выделенную в примере 1 выше, мы вводим:  
    `delete ptr;`  
    Аналогично, например, память может быть освобождена:  
    `delete ptr2` ;
    
    ### Утечки памяти
    
    Утечки вызывают, когда вы не можете освободить динамическую память, которую вы выделили с помощью оператора `New` в конце вашей программы. Если вы не освободите его с помощью оператора Delete, ваш компьютер будет продолжать создавать новую память в куче каждый раз, когда запускается программа. Это приводит к замедлению работы вашего компьютера, поскольку память не удаляется, а доступная память уменьшается.