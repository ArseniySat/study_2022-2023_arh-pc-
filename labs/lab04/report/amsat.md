﻿**Лабораторная работа №4**

**Архитектура вычислительных систем**

Арсений Сат
# Содержание

# **1	Цель работы**
Освоение процедуры компиляции и сборки программ, написанных на ассем- блере NASM.
# **2	Задание**
1. В соответствующем каталоге сделайте отчёт по лабораторной работе №4 в формате Markdown. В качестве отчёта необходимо предоставить отчёты в 3 форматах: pdf, docx и md.
1. Загрузите файлы на github.
# **3	Теоретическое введение**
Здесь описываются теоретические аспекты, связанные с выполнением работы.

Например, в табл. 1 приведено краткое описание стандартных каталогов Unix.

*Таблица 1: Описание некоторых каталогов файловой системы GNU Linux*

|Имя каталога|Описание каталога|
| :- | :- |
|/|Корневая директория, содержащая всю файловую|
|/bin|Основные системные утилиты, необходимые как в однопользовательском режиме, так и при обычной работе всем пользователям|
|/etc|Общесистемные конфигурационные файлы и файлы конфигурации установленных программ|
|/home|Содержит домашние директории пользователей, которые, в свою очередь, содержат персональные настройки и данные пользователя|
|/media|Точки монтирования для сменных носителей|
|/root|Домашняя директория пользователя root|
|/tmp|Временные файлы|
|/usr|Вторичная иерархия для данных пользователя|
Более подробно об Unix см. в [1–6].
# **4	Выполнение лабораторной работы**
1) Создаём каталог для работы с программами на языке ассемблера NASM:

![](Aspose.Words.44b46578-f7d7-472b-93d7-b6a56d86f4c0.001.png)

*Рис. 1: создание каталога*

2) Создаём текстовый файл с именем hello.asm и открываем этот файл с помощью любого текстового редактора gedit

![](Aspose.Words.44b46578-f7d7-472b-93d7-b6a56d86f4c0.002.png)

*Рис. 2: файл hello.asm*

![](Aspose.Words.44b46578-f7d7-472b-93d7-b6a56d86f4c0.003.png)

*Рис. 3: gedit*

3) Вводим в него следующий текст:

![](Aspose.Words.44b46578-f7d7-472b-93d7-b6a56d86f4c0.004.png)

*Рис. 4: файл*

4)NASM превращает текст программы в объектный код. Например, для компиляции приведённого выше текста программы «Hello World» необходимо написать следующее:

![](Aspose.Words.44b46578-f7d7-472b-93d7-b6a56d86f4c0.005.png)

*Рис. 5: успешная компиляция*

5)Т. к. текст программы набран без ошибок, транслятор преобразует текст программы из файла hello.asm в объектный код, который записан в файл hello.o.

![Рис. 6: транслятор](Aspose.Words.44b46578-f7d7-472b-93d7-b6a56d86f4c0.006.png)

*Рис. 6: транслятор*

6) С помощью команды ls проверим, что объектный файл был создан. У нас есть два файла hello.asm и hello.o.

![](Aspose.Words.44b46578-f7d7-472b-93d7-b6a56d86f4c0.007.png)

*Рис. 7: ged it report.md*

7) Следующая команда скомпилирует исходный файл hello.asm в obj.o , при этом формат выходного файла будет elf, и в него будут включены символы для отладки (опция -g), кроме того, создается файл листинга list.lst .Выполним следующую команду:

*Рис. 8: картинки*

8) С помощью команды ls проверим, что файлы были созданы:

*Рис. 9: ls*

10)Для получения списка форматов объектного файла смотрим nasm -hf.

![](Aspose.Words.44b46578-f7d7-472b-93d7-b6a56d86f4c0.008.png)*Рис. 10: -hf*

11)Чтобы получить исполняемую программу, объектный файл необходимо передать на обработку компоновщику, а потом с командой ls проверим содержимое:


*Рис. 11: ls*

12) Ключ -o с последующим значением задаст в данном случае имя создаваемого исполняемого файла. Выполним следующую команду:

![](Aspose.Words.44b46578-f7d7-472b-93d7-b6a56d86f4c0.009.png)


![](Aspose.Words.44b46578-f7d7-472b-93d7-b6a56d86f4c0.010.png)

*Рис. 12: Ключ -о*

11)Запустим на выполнение созданный исполняемый файл, находящийся в текущем каталоге, набрав в командной строке ./hello:

![](Aspose.Words.44b46578-f7d7-472b-93d7-b6a56d86f4c0.011.png)

*Рис. 13: файл*
# **5	Выполнение самостоятельной работы**
1) В каталоге ~/work/arch-pc/lab04 с помощью команды cp создали копию файла hello.asm с именем lab04.asm.

![](Aspose.Words.44b46578-f7d7-472b-93d7-b6a56d86f4c0.012.png)

*Рис. 14: 111.png*

2) С помощью текстового редактора внесли изменения в текст программы в файле lab04.asm так, чтобы вместо Hello world! на экран выводилась строка с фамилией и именем. Для этого вместо “Hello world” пишу “amsat”.

![](Aspose.Words.44b46578-f7d7-472b-93d7-b6a56d86f4c0.013.png)

*Рис. 15: 222.png*

![](Aspose.Words.44b46578-f7d7-472b-93d7-b6a56d86f4c0.014.png)

*Рис. 16: 223.png*

3) Оттранслируем полученный текст программы lab04.asm в объектный файл и запустим, получим вывод фамилии и имени.

*Рис. 17: 333.png*

4) Загружаю файлы на GitHub при помощи команд “git add .”, “git commit -am”” “,”git push”.

![](Aspose.Words.44b46578-f7d7-472b-93d7-b6a56d86f4c0.015.png)

*Рис. 18: 0.png*
# **6	Выводы**
Я освоила процедуру компиляции и сборки программ, написанных на ассемблере NASM (рассмотрела пример простой программы, научилась изменять внутрисодержимое файла, приобрела навык по созданию объектных файлов).
# **Список литературы**
\1. 	GNU Bash Manual [Электронный ресурс]. Free Software Foundation, 2016. URL: <https://www.gnu.org/software/bash/manual/>.

\2. 	Newham C. [Learning the bash Shell: Unix Shell Programming](http://www.amazon.com/Learning-bash-Shell-Programming-Nutshell/dp/0596009658). O’Reilly Media, 2005. 354 с.

\3. 	Zarrelli G. Mastering Bash. Packt Publishing, 2017. 502 с.

\4. 	Robbins A. [Bash Pocket Reference](https://www.ncbi.nlm.nih.gov/pubmed/25246403). O’Reilly Media, 2016. 156 с.

\5. 	Таненбаум Э. Архитектура компьютера. 6-е изд. СПб.: Питер, 2013. 874 с.

\6. 	Таненбаум Э., Бос Х. Современные операционные системы. 4-е изд. СПб.: Питер, 2015. 1120 с.