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
if [ -z "$1" ]; then
    echo "Usage: $0 \"Your message here\""
    exit 1
fi

message="$1"

length=${#message}

border="+$(printf -- '-%.0s' $(seq 1 $((length + 2))))+"

echo "$border"
echo "| $message |"
echo "$border"
```

![Снимок экрана 2024-09-09 225353](https://github.com/user-attachments/assets/4727766e-ada3-49c1-9ca8-d4fffa402df9)

## Объяснение
if [ -z "$1"]; then... - если при вызове скрипта поле ввода пустое то мы выводим условия выполнения скрипта  
message="$1" - присваивам аргументу название message  
length=${#message} - вычисляем длину строки  
border="+$(printf -- '-%.0s'(seq1((length + 2))))+" - Создание рамок  
printF -- '-%.0s' - печать символа '-'  
(seq1((length + 2))) - вывод символа '-' от 1 до length + 2  

## Задача 4
