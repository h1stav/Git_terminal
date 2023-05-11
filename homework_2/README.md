# Homework_2

1. _Сделать папку **dir_1**_
```
$ mkdir dir_1
```
2. _Зайти в папку **dir_1**_
```
$ cd dir_1
```
3. _Сделать папку **inner_dir_1**_
```
$ mkdir inner_dir_1
```
4. _Посмотреть где ты находишься_
```
$ pwd
```
**Result**
```
/c/Users/Денис/Desktop/terminal/dir_1
```
5. _Находясь в папке **dir_1** создать пустой текстовый файл **tf_1.txt**_
```
$ touch tf_1.txt
```
6. _Находясь в папке **dir_1** через команду **cat** создать текстовый файл **tf_2.txt** со следующими 
строками: 

- the first 1
- the second 2
- the third 3

```
$ cat > tf_2.txt
- the first 1
- the second 2
- the thing 3
```
7. _Зайти в папку **inner_dir_1**_
```
$ cd inner_dir_1
```
8. _Через cat сделать текстовый файл **tf_3.txt**  c любыми строками_
```
$ cat > tf_3.txt
I'm waking up to ash and dust
I'm wipe my brow and sweat my rust
I'm breathing in the chemicals
```
9. _Через **cat** добавить в текстовый файл **tf_3.txt** строку “the second 2”_
```
$ cat >> tf_3.txt
the second 2
```
10. _Через **cat** добавить в текстовый файл **tf_3.txt** строку “the sec 2”_
```
$ cat >> tf_3.txt
the sec 2
```
11. _Через **cat** добавить в текстовый файл **tf_2.txt** строку “the sec 3”_
```
$ cat >> ../tf_2.txt
the sec 3
```
12. _Через **cat** добавить в текстовый файл **tf_3.txt** строку “the SeCoNd 2”_
```
$ cat >> tf_3.txt
the SeCoNd 2
```
13. _Через **cat** добавить в текстовый файл **tf_2.txt** строку “the seConD 2”_
```
$ cat >> ../tf_2.txt
the seConD 2
```
14. _Сделать текстовый файл **tf_4.txt** в котором будет 15 строк_

15. _Сделать текстовый файл **tF_5.txt** в котором будет 13 строк_

16. _Вывести список всех файлов в папке_
```
$ ls
```
Result
```
tf_3.txt  tf_4.txt  tf_5.txt
```
17. _Выйти из папки **inner_dir_1**_
```
$ cd ..
```
18. _Вывести содержимое файла **tf_3.txt** в терминал_
```
$ cat inner_dir_1/tf_3.txt
I'm waling up to ash and dust
I'm wipe my brow and sweat my rust
I'm breathing in the chemicals
the second 2
the sec 2
the SeCoNd 2
```
19. _Найти путь к файлу **tf_4.txt**_
```
$ find -name tf_4.txt
```
Result
```
./inner_dir_1/tf_4.txt
```
20. _Отчистить файл **tf_4.txt** от содержимого без удаления самого файла_
```
$ > inner_dir_1/tf_4.txt
```
21. _Найти путь к файлам у которых есть  **“tf”** в названии_
```
$ find -type f -name "tf*"
```
Result
```
./inner_dir_1/tf_3.txt
./inner_dir_1/tf_4.txt
./tf_1.txt
./tf_2.txt
```
22. _Найти путь к файлам у которых есть  **“tf”** в названии и буквы в любом регистре_
```
$ find -type f -iname "tf*"
```
Result
```
./inner_dir_1/tf_3.txt
./inner_dir_1/tf_4.txt
./inner_dir_1/tF_5.txt
./tf_1.txt
./tf_2.txt
```


