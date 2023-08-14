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
the first 1
the second 2
the thing 3
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
```
$ seq 15 | cat >> tf_14.txt
```
16. _Сделать текстовый файл **tF_5.txt** в котором будет 13 строк_
```
$ seq 13 | cat >> tF_5.txt
```
17. _Вывести список всех файлов в папке_
```
$ ls
```
Result
```
tf_3.txt  tf_4.txt  tF_5.txt
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
23. _Найти строки в файлах где есть комбинация букв **“sec”** в текущей папке._
    
_Для поиска слова ‘sec’ во всех файлах текущей директории достаточно использовать подстановочный знак (*)_
```
$ grep sec *
```
Result
```
tf_2.txt:the second 2
tf_2.txt:the sec 3
```
24. _Найти строки в файлах где есть комбинация букв **“sec”** в любом регистре в текущей папке._
    
 _Используем уже известный нами ключ_ **-i**
 
```
$ grep -i sec *
```
Result
```
tf_2.txt
```
25. _Найти строки в файлах где есть только комбинация букв **“sec”** в текущей папке._
    
_Для поиска только определенной комбинации букв, нужно  использовать ключ **-w**_

```
$ grep -w sec *
```
Result
```
tf_2.txt:the sec 3
```
26. _Найти строки в файлах где есть только комбинация букв **“sec”** в любом регистре в текущей папке_
```
$ grep -wi sec *
```
Result
```
tf_2.txt:the sec 3
```
27. _Найти строки в файлах где есть комбинация букв **“second”** в текущей папке_
```
$ grep second *
```
Result
```
tf_2.txt:the second 2
```
28. _Найти строки в файлах где есть комбинация букв **“second”** в любом регистре в текущей папке_
```
$ grep -i second *
```
Result
```
tf_2.txt:the second 2
tf_2.txt:the seConD 2
```
29. _Найти строки в файлах где есть комбинация букв **“second”** во всех папках ниже уровнем._
    
_С этой опцией **-r**, grep будет искать все файлы в текущем (или указанном) каталоге, а также все файлы во всех подкаталогах_

```
$ grep -r second ./*/
```
Result
```
./inner_dir_1/tf_3.txt:the second 2
```
30. _Найти только путь и название файла в строках которых есть комбинация букв **“second”** в текущей папке._

_С опцией -l, выводить только имена файлов_

_Чтобы найти путь к файлу используем команду **xargs realpath**_

```
$ grep -l second *|xargs realpath
```
Result
```
/c/Users/Денис/Desktop/terminal/dir_1/tf_2.txt
```
31. _Найти все строки во всех файлах где нет комбинации **“second”**_

_Еще одна полезная опция grep - это ключ **-v**, выводит только те строки, в которых шаблон поиска не найден_
```
$ grep -rv second
```
Result
```
inner_dir_1/tf_3.txt:I'm waling up to ash and dust
inner_dir_1/tf_3.txt:I'm wipe my brow and sweat my rust
inner_dir_1/tf_3.txt:I'm breathing in the chemicals
inner_dir_1/tf_3.txt:the sec 2
inner_dir_1/tf_3.txt:the SeCoNd 2
tf_2.txt:the first 1
tf_2.txt:the thing 3
tf_2.txt:the sec 3
tf_2.txt:the seConD 2
```
32. _Найти только название и путь к файлам где нет комбинации **“second”**_
```
$ grep -rvl second | xargs realpath
```
Result
```
/c/Users/Денис/Desktop/terminal/dir_1/inner_dir_1/tf_3.txt
/c/Users/Денис/Desktop/terminal/dir_1/tf_2.txt
```
33. _Вывести в терминал 4 последних строк любого текстового файла_
```
$ tail -n 4 inner_dir_1/tf_3.txt
```
Result
```
I'm breathing in the chemicals
the second 2
the sec 2
the SeCoNd 2
```
34. _Вывести в терминал 4 первые строки любого текстового файла_
```
$ head -n 4 inner_dir_1/tf_3.txt
```
Result
```
I'm waling up to ash and dust
I'm wipe my brow and sweat my rust
I'm breathing in the chemicals
the second 2
```
35. _Команда в одну строку. Создать папку и создать текстовый файл с содержимым_
```
$ mkdir one && cat >> one.txt
Iphone
Ipad
ipod
airpods
```
36. _Команда в одну строку. Переместить в любую одну папку текстовые файлы у которых в содержимом есть слово **“sec”**_
```
$ grep -rwl sec | xargs mv -t inner_dir_1
```
37. _Команда в одну строку. Скопировать в любую одну папку текстовые файлы у которых в содержимом есть слово **“sec”**_
```
$ grep -rwl sec | xargs cp -t inner_dir_1
```
Result
```
cp: 'inner_dir_1/tf_2.txt' and 'inner_dir_1/tf_2.txt' are the same file
cp: 'inner_dir_1/tf_3.txt' and 'inner_dir_1/tf_3.txt' are the same file
```
38. _Команда в одну строку. Найти все строки c **“sec”** во всех текстовых файлах, скопировать и вставить эти строки в один новый созданный текстовый файл_
```
$ grep -rwl sec >>new.txt
```
39. _Команда в одну строку. Удалить текстовые файлы у которых в содержимом есть слово **“sec”**_
```
$ grep -rwl sec |xargs rm
```
40. _Просто вывести в терминал строку **“Good job!!”**_
```
$ echo 'Good Job!!'
```
Result
```
Good Job!!
```
