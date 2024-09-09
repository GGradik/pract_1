# Практическое занятие №1. Введение, основы работы в командной строке

## Задача 1

`cut -d: -f1 /etc/passwd |sort`

![Снимок экрана 2024-09-09 221326](https://github.com/user-attachments/assets/a9e24d0d-8875-40fc-85bf-fa6e50f90ebb)


## Объяснение
cut -d: -f1 /etc/passwd — команда cut извлекает первый столбец из файла /etc/passwd, используя двоеточие : как разделитель полей и выводит его.  
sort — сортирует строки в алфавитном порядке.  

## Задача 2

`awk '{print $2, $1}' /etc/protocols | sort -k1,1nr | head -n 5`

![Снимок экрана 2024-09-09 223710](https://github.com/user-attachments/assets/6535b5d5-5095-4c36-be1a-e2279a68c594)


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

![Снимок экрана 2024-09-09 225353](https://github.com/user-attachments/assets/4727766e-ada3-49c1-9ca8-d4fffa402df9)

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
## code is presented in the file code/hello.go

![Снимок экрана 2024-09-10 003521](https://github.com/user-attachments/assets/facc53b8-3544-4299-9b40-303a3cc19e2a)

## Задача 5

```
chmod +x reg  
./reg banner
```

## code is presented in the file bash/banner and bash/reg

![Снимок экрана 2024-09-10 003647](https://github.com/user-attachments/assets/11d53133-f2f5-4c68-a380-8739f06963ba)

## Задача 6

```
chmod +x check_comment.sh  
./check_comment.sh
```

## code is presented in the file bash/check_comment.sh

![Снимок экрана 2024-09-10 003816](https://github.com/user-attachments/assets/8fed27df-fb4e-46fe-a439-2b7d53c3c80b)

## Задача 7

```
chmod +x find_duplicates.sh  
./find_duplicates.sh /Users/aslav/Documents/cdr
```

## code is presented in the file bash/find_duplicates.sh

![Снимок экрана 2024-09-10 003916](https://github.com/user-attachments/assets/d7fd1837-8044-4ba7-83e7-e98eecc5e355)

## Задача 8

```
go run archiver.go /Users/aslav/Documents/cdr  .log
```

## code is presented in the file code/archiver.go

![Снимок экрана 2024-09-10 004010](https://github.com/user-attachments/assets/57d0cc98-8e1a-44ef-94c6-6bd8326628d7)

## Задача 9

```
cd code  
go run replacer.go /Users/aslav/Desktop/RTU_MIREA_2COURCE/КонфигУправ/1Pract/trash/testFor8.txt   testFor8output.txt
```
## code is presented in the file code/replacer.go

![Снимок экрана 2024-09-10 004110](https://github.com/user-attachments/assets/8935421e-6892-425a-9e99-74c2893bbc70)

![Снимок экрана 2024-09-10 004131](https://github.com/user-attachments/assets/5660e64f-a179-48da-ae79-4b9021896151)

## Задача 10

```
cd code  
go run dirReader.go /Users/aslav/Downloads 
```

## code is presented in the file code/dirReader.go

![Снимок экрана 2024-09-10 004218](https://github.com/user-attachments/assets/f0959d0a-1215-487a-bfc5-372d6dcbac53)
