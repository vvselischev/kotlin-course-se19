# ДЗ04 - Fun debugger

**Это дополнительное задание, выполнять его можно по желанию**

За выполнение задания до дедлайна вы получаете дополнительные баллы (как если бы это было обязательное задание).

**Дедлайн**: 25.10.2018 23:59 

Необходимо реализовать дебаггер для интерпретатора из задания `02-fun-interpeter`.
Дебаггер должен представлять собой отдельную консольную утилиту, работающую в режиме
REPL.
Должен быть поддержан следующий набор команд:
- `load <filename>` – загружает код программы в память. Если до этого был загружен
другой файл, то его интерпретация отменяется, все брейкпойты очищаются.
- `breakpoint <line-number>` – устанавливает брейкпойт на указанной строке.
- `condition <line-number> <condition-expression>` – устанавливает
условный брейкпойт на указанной строке. Если на этой строке уже был брейкпойнт,
то он заменяется на новый.
- `list` – выводит список брейкпойнтов с номерами строк и условиями
- `remove <line-number>` – удаление брейкпойнта по номеру строки
- `run` – запуск загруженного файла. Все, что выводится через `println`, должно
попадать в консоль. Если исполнение дошло до строки с брейкпойнтом
(и его условие, исполненное в соответствующем контексте вернуло `1`), то интерпретация
программы приостанавливается. В случае, если программа уже была запущена ранее, выводится ошибка.
- `evaluate <expression>` – вычисление значения произвольного выражения в контексте,
где произошла остановка по брейкпойнту
- `stop` – остановка исполнения текущей программы
- `continue` – продолжение исполнения текущей программы до следующего брейкпойнта
или до ее завершения
## Требования к решению
- Pull request должен состоять из двух коммитов
  - Проверенное решение ДЗ `02-fun-interpreter`
  - Изменения в коде, необходимые для реализации задания
- Для реализации приостановки программы нужно воспользоваться корутинами
- Функциональность остановки на брейкпойнтах (в т.ч. условных) и продолжения программы
должна быть покрыта юнит-тестами