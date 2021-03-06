
# Задача

Разработать командный интерпретатор для работы с файловой системой Unix.

## Требования

1. Программа в бесконечном цикле считывает из потока ввода строки, каждая из
   которых содержит имя команды и аргументы. Программа передает исполнение
   команды соответствующей функции **run_\<command_name\>**.
   Все аргументы команд являются обязательными.

2. Команда **touch \<filename\>** создает
   файл **\<filename\>**, если он отсутствует.

3. Команда **echo \<value\> > \<filename\>** записывает строку **\<value\>**
   в файл **\<filename\>**. Исходное содержимое файла удаляется.
   Если файл отсутствует, программа создает его. Программа обрабатывает
   две специальные последовательности внутри **\<value\>**:
   '\\n' добавляет переход на новую строку, '\\b' удаляет предшествующий символ.

4. Команда **cat < \<filename\>** выводит в терминал
   содержимое файла **\<filename\>**.

5. Команда **ls \<pattern\>** выводит в терминал список файлов,
   которые находятся в текущем каталоге и чье имя соответствует
   шаблону **\<pattern\>**. Шаблон **\<pattern\>** является упрощенной версией
   шаблонов в Unix shell. Если в шаблоне есть символ '\*', он совпадает с любой
   последовательностью символов в имени файла. Символ '\*' может использоваться
   не больше одного раза. Все остальные символы шаблона должны совпадать с
   соответствующими символами в имени файла.

# Упрощенная задача

Не реализовывать команду **ls**.

# Наблюдение результатов

Находясь в директории лабораторной работы запустите командный интерпретатор:

```console
./lab_02
```

Проверьте работу команды **ls**:

```console
> ls lab_*
lab_02.c
lab_02.c.template
lab_02
lab_02.o
```

Проверьте работу команды **touch**:

```console
> touch test.txt
> ls *.txt
test.txt
```

Проверьте работу команд **echo** и **cat**:

```console
> echo Hello!!\b\nWorld! > ./test.txt
> cat < ./test.txt
Hello!
World!
```
