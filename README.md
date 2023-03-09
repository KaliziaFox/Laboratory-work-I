# Laboratory-work-I
# Лабораторная работа №1. Выполнена студенткой МГТУ имени Н.Э. Баумана группы ИУ8-23 Калугиной Елизаветой.
# 1) Скачивание библиотеки boost:
wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
# 2) Разархивация:
tar -xf boost_1_69_0.tar.gz
# 3) Количество файлов в директории, не включая вложенные директории:
find . -maxdepth 1 -type f| wc

Итог: 12 файлов
# 4) Количество файлов в директории, включая вложенные директории:
find . -type f| wc

Итог: 61191 файл
# 5) Кол-во файлов с расширением .cpp:
find . -name "*.cpp" | wc

Итог:13774 файла
# Количество заголовочных файлов .hpp, .h:
find . -name "*.hpp" -o -name "*.h" | wc

Итог:15208 файлов

# Кол-во остальных файлов (не заголовочных и не .cpp):
find -not -name "*.cpp" -not -name "*.hpp" -not -name "*.h" -type f | wc

Итог: 32209 файлов

# 6) Полный путь до файла any.hpp внутри библиотеки boost:

find . -name "any.hpp"

# 7) Список файлов, в которых упоминается последовательность boost::asio:

grep -lr boost::asio

# 8) Компиляция boost:

./bootstrap.sh --prefix=boost_output --with-python=python3 --with-icu=

Поддержка Python 3.x и Unicode

./b2 install

Фактическая сборка, компилирование

# 9) Перенос все скомпилированных на предыдущем шаге статические библиотеки в директорию ~/boost-libs:

mkdir ~/boost-libs 

cd ~/boost_1_69_0/boost_output/lib

mv * ~/boost-libs
