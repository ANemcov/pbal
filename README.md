#**pbal.sh**

##скрипт проверки состояния баланса сотовых операторов и итнернет провайдеров.  

*На 23.01.2015*

- intertelecom.ua - itc_ua
- Corbina (Beeline-internet) - corbina
- МТС (через мобильные сайты) - mts_pda

*На 01.11.2012*

- kyivstar.ua

*На 26.10.2012*

- qiwi.ru

*На 26.09.2011 поддерживаются следующие операторы:*

- moscowsg.megafon.ru
- mts.ru
- beeline.ru
- mgts.ru
- onlime.ru

Зависимости:

- curl
- iconv
- sed
- awk

Установка:
скопировать скрипт туда где удобно и сделать его исполняемым: chmod +x pbal.sh

Ключи:
-t — тайм аут для соединения в секундах 
-a — количество попыток соединения
-T — тайм аут между попытками соединения
-s — тихий режим, не выводит сообщения об ошибках
-v — выводить информацию о операторе и логине вместе с балансом

Примеры использования:

./pbal.sh mts 9164444444 1111
64.53

./pbal.sh -v beeline 9031222222 22222
beeline 9031222222 0.00

./pbal.sh -t10 -a1 -T5 -v onlime 15055555 1222222222
onlime 15055555 537.71

./pbal.sh qiwi +79265552211
Password:
3763.77

./pbal.sh -v kyivstar +380677775555
Password: 
kyivstar +380677775555 25.17


В каталоге web скрипт для сбора статистики в БД sqlite и генерация статичных HTML страниц отчетов
скрипт pbalweb.sh настраивается под свои нужды и запускается по крону
