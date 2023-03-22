# CodeLang

## Часть 1.

1. Тип приложения - веб-приложение
2. Стратегия развертывания: развертывание Docker-контейнеров на облачном сервисе.
3. Технологии:
- **Frontend**: `Vue.js` (реактивность + работа с нативным HTML)
- **Backend**: `Django` + `SQLite` (расширяемость)

4. Показатели качества:
- **Качества дизайна**: возможность повторного использования
- **Качества времени выполнения**: масштабируемость
- **Качества системы**: тестируемость
- **Качества взаимодействия с пользователем**: удобство и простота использования

5. Пути реализации сквозной функциональности:
- Инструментирование и протоколирование: с помощью встроенного в **Nest.js** класса **Logger**
- Аутентификация: с использованием библиотеки `django.contrib.auth` и реализации стратегии аутентификации через `JWT`
- Управление исключениями: с использованием предоставляемых фреймворком **Exceptions filters**
- Связь: с использованием протокола `HTTP` и `WebSocket`
- Валидация: на клиентской части — `VeeValidate` и `Yup`, на сервере — `Django models` и `serializers`

### Диаграмма компонентов

![Диаграмма компонентов](components.jpeg)

### Диаграмма развертывания

![Диаграмма развертывания](deployment.png)

## Часть 2.

### Диаграмма классов

![Диаграмма классов](classes.png)

## Часть 3.

1. Отличия архитектур "As is" и "To be", и причины:
  - Если сравнивать архитектуры в целом (будем рассматривать архитектуры серверной части), то итоговая "As is" архитектура придерживается той реализации, которая изображена на диаграмме компонентов "To be" архитектуры. "As is" архитектура является более детальной, здесь присутствует множество различных контроллеров, сервисов, валидаторов, представленных на "To be" диаграмме компонентов в виде единичных сущностей.

2. Пути улучшения архитектуры:
   - Следует принять определенный стиль написания кода и соглашение о присваивании имен для разработки.
   - Не смешивать разные типы компонентов на одном логическом уровне
   - Максимально изолировать сквозную функциональность от бизнес-логики приложения
