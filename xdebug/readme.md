#### Минимальный конфиг для запуска xdebug + phpstorm

1. Запустить встроенный php сервер:
    php -S localhost:8000
2. В Chrome включить плагин XdebugHelper
3. php -v должен давать инфу о подключенном xdebug
4. В настройках phpstorm php выбрать cli php с xdebug
5. Включить трубку, поставить брейкпойнт