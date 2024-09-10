# Практическое занятие №1. Введение, основы работы в командной строке

## Задача 1

`cut -d: -f1 /etc/passwd |sort`

![image](https://github.com/user-attachments/assets/b9adca4b-0a51-4392-951a-5a5dddcf50be)

## Объяснение
cut -d: -f1 /etc/passwd — команда cut извлекает первый столбец из файла /etc/passwd, используя двоеточие : как разделитель полей и выводит его.  
sort — сортирует строки в алфавитном порядке.  

## Задача 2

`awk '{print $2, $1}' /etc/protocols | sort -k1,1nr | head -n 5`

![image](https://github.com/user-attachments/assets/587ca106-49aa-42eb-80dd-8d9e3bc7d64f)

## Объяснение
awk '{print $2, $1}' /etc/protocols: Эта команда извлекает второй столбец и первый столбец из файла /etc/protocols и выводит их в формате номер имя.  
sort -k1,1nr: Сортирует вывод по первому столбцу численно и в обратном порядке.  
head -n 5: Выводит только первые пять строк.  

## Задача 3

```
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
```

![image](https://github.com/user-attachments/assets/48ccb2d2-b867-4c3f-843b-c58b0d806746)

## Объяснение

```
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
```
## Задача 4

```
grep -oE '\b[a-zA-Z_][a-zA-Z0-9_]*\b' hello.go | grep -vE '\b(int|void|return|if|else|for|while|include|stdio)\b' | sort | uniq
```

![image](https://github.com/user-attachments/assets/50793247-9e32-4a04-ac24-fd0d7ae38357)

## Задача 5

```
chmod +x reg  
./reg banner
```

![image](https://github.com/user-attachments/assets/3ea841f2-6e57-4fc4-b5bb-bd635ebc2f2b)

## Задача 6

```
chmod +x check_comment.sh  
./check_comment.sh
```

![image](https://github.com/user-attachments/assets/f3b6a7cf-4010-4137-82a1-f8195d80e4a1)

## Задача 7

```
chmod +x find_duplicates.sh  
./find_duplicates.sh /Users/aslav/Documents/cdr
```

![image](https://github.com/user-attachments/assets/4e0968c3-a7a3-43da-8ec5-0f6517b507cd)

## Задача 8

```
go run archiver.go /Users/aslav/Documents/cdr  .log
```


![image](https://github.com/user-attachments/assets/81ad612a-d882-4d35-a969-c7d52a8714ad)

## Задача 9

```
cd code  
go run replacer.go /Users/aslav/Desktop/RTU_MIREA_2COURCE/КонфигУправ/1Pract/trash/testFor8.txt   testFor8output.txt
```

![image](https://github.com/user-attachments/assets/8ee4a9cf-a9cf-4013-956e-c5ef9b3bdac8)
![image](https://github.com/user-attachments/assets/b157cf98-9f8b-4c03-8eeb-482086a6b609)

## Задача 10

```
cd code  
go run dirReader.go /Users/aslav/Downloads 
```

![image](https://github.com/user-attachments/assets/219c6b50-41dc-4c09-b894-7b93830f882a)
