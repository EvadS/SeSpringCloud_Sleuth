# SeSpringCloud_Sleuth

## Spring Cloud Sleuth + Zipkin

Spring Cloud Sleuth нужен для трассировки логов в вашем приложении.
Это “как-бы” надстройка для Spring Cloud и принадлежит к семейству проектов Spring Cloud.
Позволяет легко идентифицировать журналы, связанные с конкретной работой, запросом или потоком.
Он легко интегрируется с Logback, SLF4J и т.д.

 информация, добавленная Sleuth в формате
### [application name, traceId, spanId, export]

где
* <b>application name</b> — это имя приложения, указанное в application.yml
* <b>traceId</b> — ID, назначаемый каждому запросу.
* <b>spanId</b> — используется для отслеживания работы. Каждый запрос может иметь несколько шагов, каждый шаг имеет свой уникальный spanId.
* <b>export</b> — это флаг, который указывает, следует ли экспортировать определенный журнал в инструмент агрегирования журналов, такой как Zipkin.

#Zipkin
docker run -d -p 9411:9411 openzipkin/zipkin

По умолчанию Zipkin работает по адресу
localhost: 9411

Перенастроить порт можно в файле настроек (application.properties):
spring.zipkin.baseUrl=…