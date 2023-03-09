# Homework_01
### #Task_1
> получил архив через скачивание
`wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`
### #Task_2
> разархировал 
`tar -xzvf boost_1_69_0.tar.gz`
```
Для команды tar:
 -x извлекает файлы из архива
 -z перенаправить вывод в команду gzip 
 -v выводит подробную информацию процесса
 -f вывести результат в файл
 ```
### #Task_3
> для удобства перейду в каталог boost_1_69_0
`cd boost_1_69_0`
> выведу дерево файлов и папок
  `tree -aL 1` 
 ```
 Для команды tree:
	-a выводить все файлы
	-L устанавливает максимальный уровень вложенности равной единице
```
  Ответ: **6 directories, 12 files**
### #Task_4
>вывел все файлы и папки `tree -a`

Ответ: **5637 directories, 61191 files**
### #Task_5
> Найду количество файлов с расширением .cpp  `find ! -type d -name "*.h" | wc `

Ответ: **13774**
```
Для команды find
-name поиск по имени
-type f поиск по файлам
Для команды wc - считает колличество
-l считает кол-во строк
```
> Найду количество заголовочных файлов, т.е. с расширением .hpp и .h `find ! -type d -name "*.cpp" | wc` 
 
 Ответ: **15208**
 
 > Найду кол-во остальных файлов `find ! -type d ! -name "*.cpp" ! -name "*.h" | wc`
 
Ответ: **32209**

### #Task_6

> Найду путь до файла с именем 'any.hpp' `find -name 'any.hpp'`

```
Получившиеся варианты:
  ./boost/hana/fwd/any.hpp
  ./boost/hana/any.hpp
  ./boost/spirit/home/support/algorithm/any.hpp
  ./boost/fusion/include/any.hpp
  ./boost/fusion/algorithm/query/detail/any.hpp
  ./boost/fusion/algorithm/query/any.hpp
  ./boost/type_erasure/any.hpp
  ./boost/proto/detail/any.hpp
  ./boost/any.hpp
  ./boost/xpressive/detail/utility/any.hpp
```

### #Task_7
 > Вывожу файлы, в которых упоминается последовательность 'boost::asio' `grep -rl 'boost::asio'`
 
 ```
Для команды grep - ищет внитри файла:
 -r рекурсия(поиск в файлах каталога/подкаталога)
 -l выводит только файлы
```

> Применив `grep -rl 'boost::asio' |wc -l`, узнал кол-во файлов, где эта последовательность (1763)

### #Task_8

 > Следуя инструкции из ссылки скомпилировал boost:
   `./bootstrap.sh`,
   `./b2 install` (--prefix=путь к файлу), так как не выполнил команду --prefix, то пришлось узнать какие файлы новые.
	 
### #Task_9
 > Перехожу в корневую папку `cd ~`. Создаю там папку `mkdir boost-libs`. Перемещаю нужные файлы (1 папка и 4 файла) `mv bin.v2 ~/boost-libs`
 
### #Task_10
> Посмотреть рамер файлов в каталоге/подкаталогах `du -ah`

```
Для команды du
 -a размер для всех файлов
 -h размер в единицах измерения
```

### #Task_11
> Вывел топ 10 самых тяжёлых файлов `find ! -type d -exec du {} + | sort -rn | head -n 10`
    
```
-exec {} + — для каждого найденного файла выполняется команда
sort - сортировка
-r - сортировать в обратном порядке
-n - сортировка строк linux по числовому значению
head -n 10 отсортировать 10 строк
```
