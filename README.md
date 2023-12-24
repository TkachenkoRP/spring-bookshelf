# Книжная полка

Это приложение представляет собой CRUD-приложение для управления книгами, разработанное с использованием Spring MVC, Spring Data JPA и Spring Boot Redis. В проекте используются две основные сущности: Book (Книга) и Category (Категория). Связь между книгами и категориями в базе данных представлена как один к одному (у каждой книги может быть только одна категория).

Важные особенности приложения:

* Категории создаются только вместе с книгой, и CRUD-операции для сущности Category не реализуются.
* Реализованы следующие эндпоинты:
  * Поиск одной книги по её названию и автору
  * Получение списка книг по имени категории
  * Создание книги
  * Обновление информации о книге
  * Удаление книги по её ID

Технические особенности:

* В сервисном слое реализован механизм кеширования с использованием Redis для метода поиска книги по названию и автору, а также для метода поиска коллекции книг по имени категории.
* Методы создания, обновления и удаления книг инвалидируют соответствующие кеши, заполненные при поиске сущностей, осуществляя инвалидацию кешей по их ключу.