Практическое занятие №1. Введение, основы работы в командной строке
Задача 1
cut -d: -f1 /etc/passwd |sort

Снимок экрана 2024-09-09 221326

Объяснение
cut -d: -f1 /etc/passwd — команда cut извлекает первый столбец из файла /etc/passwd, используя двоеточие : как разделитель полей и выводит его.
sort — сортирует строки в алфавитном порядке.

Задача 2
awk '{print $2, $1}' /etc/protocols | sort -k1,1nr | head -n 5

Снимок экрана 2024-09-09 223710

Объяснение
awk '{print $2, $1}' /etc/protocols: Эта команда извлекает второй столбец и первый столбец из файла /etc/protocols и выводит их в формате номер имя.
sort -k1,1nr: Сортирует вывод по первому столбцу численно и в обратном порядке.
head -n 5: Выводит только первые пять строк.

Задача 3
#!/bin/bash
# Проверяем, был ли передан аргумент
if [ $# -eq 0 ]; then
    echo "Использование: $0 \"Ваш текст\""
    exit 1
fi
# Получаем текст из аргумента
text="$1"
# Вычисляем длину текста
length=${#text}
# Создаем верхнюю и нижнюю границы
border=$(printf "%0.s-" $(seq 1 $((length + 2))))
border="+$border+"
# Выводим баннер
echo "$border"
echo "| $text |"
echo "$border"
Снимок экрана 2024-09-09 225353

Объяснение
#!/bin/bash
# Проверяем, был ли передан аргумент
if [ $# -eq 0 ]; then
    echo "Использование: $0 \"Ваш текст\""
    exit 1
fi
# Получаем текст из аргумента
text="$1"
# Вычисляем длину текста
length=${#text}
# Создаем верхнюю и нижнюю границы
border=$(printf "%0.s-" $(seq 1 $((length + 2))))
border="+$border+"
# Выводим баннер
echo "$border"
echo "| $text |"
echo "$border"
Задача 4
grep -oE '\b[a-zA-Z_][a-zA-Z0-9_]*\b' hello.go | grep -vE '\b(int|void|return|if|else|for|while|include|stdio)\b' | sort | uniq
code is presented in the file code/hello.go
Снимок экрана 2024-09-10 003521

Задача 5
chmod +x reg  
./reg banner
code is presented in the file bash/banner and bash/reg
Снимок экрана 2024-09-10 003647

Задача 6
chmod +x check_comment.sh  
./check_comment.sh
code is presented in the file bash/check_comment.sh
Снимок экрана 2024-09-10 003816

Задача 7
chmod +x find_duplicates.sh  
./find_duplicates.sh /Users/aslav/Documents/cdr
code is presented in the file bash/find_duplicates.sh
Снимок экрана 2024-09-10 003916

Задача 8
go run archiver.go /Users/aslav/Documents/cdr  .log
code is presented in the file code/archiver.go
Снимок экрана 2024-09-10 004010

Задача 9
cd code  
go run replacer.go /Users/aslav/Desktop/RTU_MIREA_2COURCE/КонфигУправ/1Pract/trash/testFor8.txt   testFor8output.txt
code is presented in the file code/replacer.go
Снимок экрана 2024-09-10 004110

Снимок экрана 2024-09-10 004131

Задача 10
cd code  
go run dirReader.go /Users/aslav/Downloads 
code is presented in the file code/dirReader.go
Снимок экрана 2024-09-10 004218
