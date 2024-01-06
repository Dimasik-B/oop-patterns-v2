##Шаги реализации

- #####Убедитесь в том, что создание разных представлений объекта можно свести к общим шагам.

- #####Опишите эти шаги в общем интерфейсе строителей.

- #####Для каждого из представлений объекта-продукта создайте по одному классу-строителю и реализуйте их методы строительства.

  #####Не забудьте про метод получения результата. Обычно конкретные строители определяют собственные методы получения результата строительства.
  #####Вы не можете описать эти методы в интерфейсе строителей, поскольку продукты не обязательно должны иметь общий базовый класс или интерфейс.
  #####Но вы всегда сможете добавить метод получения результата в общий интерфейс, если ваши строители производят однородные продукты с общим предком.

- #####Подумайте о создании класса директора. Его методы будут создавать различные конфигурации продуктов, вызывая разные шаги одного и того же строителя.

- #####Клиентский код должен будет создавать и объекты строителей, и объект директора. Перед началом строительства клиент должен связать определённого строителя с директором. Это можно сделать либо через конструктор, либо через сеттер, либо подав строителя напрямую в строительный метод директора.

- #####Результат строительства можно вернуть из директора, но только если метод возврата продукта удалось поместить в общий интерфейс строителей. Иначе вы жёстко привяжете директора к конкретным классам строителей.

##Преимущества
- #####Позволяет создавать продукты пошагово.
- #####Позволяет использовать один и тот же код для создания различных продуктов.
- #####Изолирует сложный код сборки продукта от его основной бизнес-логики.

##Недостатки
- #####Усложняет код программы из-за введения дополнительных классов.
- #####Клиент будет привязан к конкретным классам строителей, так как в интерфейсе директора может не быть метода получения результата.