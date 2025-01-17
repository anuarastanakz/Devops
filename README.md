# Devops
1. **Создание директории и файла:**
   Создайте директорию с именем "MyDirectory" и в этой директории создайте файл "MyFile.txt". Затем выведите список файлов и директорий в текущем каталоге.
```
mkdir MyDirectory

cd MyDirectory
touch MyFile.txt

cd ..
ls -la
```

2. **Копирование файлов:**
   Скопируйте все файлы с расширением ".txt" из одной директории в другую. Затем выведите список скопированных файлов.
```
cp /path/to/source/*.txt /path/to/destination/

ls -la /path/to/destination/*.txt
```
3. **Поиск слова:**
   Напишите скрипт, который будет искать все файлы в текущей директории и ее поддиректориях, содержащие слово "ключевое_слово". Выведите список найденных файлов.
```
grep -rl "ключевое_слово" 
```
4. **Архивирование и распаковка:**
   Создайте архив (tar) из нескольких файлов и директорий, а затем распакуйте его. Убедитесь, что файлы восстановлены корректно.
```
tar -cvf archive.tar /path/to/file1 /path/to/file2 /path/to/directory

tar -xvf archive.tar -C /path/to/extract/directory

ls -la /path/to/extract/directory
```
5. **Обработка текстового файла:**
   Создайте текстовый файл с несколькими строками текста. Напишите скрипт, который будет читать файл и выдавать каждую строку в обратном порядке.
```
echo -e "слово 1\nслово 2\nслово 3" > MyTextFile.txt

while read line; do
    echo $line | rev
done < MyTextFile.txt
```
6. **Автоматизация резервного копирования:**
   Напишите скрипт, который будет регулярно (например, каждую неделю) создавать резервные копии определенных директорий и сохранять их с датой в имени файла.
```
SOURCE_DIR="/path/to/source"

DEST_DIR="/path/to/backup"

BACKUP_FILE="$DEST_DIR/backup_$(date +%Y%m%d).tar.gz"

tar -czvf $BACKUP_FILE $SOURCE_DIR
```
7. **Подсчет количества слов:**
   Напишите скрипт, который будет принимать текстовый файл в качестве аргумента и подсчитывать количество слов в этом файле.
```
if [ -z "$1" ]; then
    echo "Использование: $0 <file>"
    exit 1
fi

wc -w $1
```
8. **Создание случайных паролей:**
   Напишите скрипт, который будет генерировать случайные пароли заданной длины и сохранять их в файл.
```
LENGTH=$1

openssl rand -base64 $LENGTH > passwords.txt
echo "Пароль сохранен в passwords.txt"
```
9. **Подсчет файлов:**
   Напишите скрипт, который будет использовать цикл for для подсчета количества файлов и директорий в текущей директории.
```
count=$(ls -1 | wc -l)
echo "Количество файлов и директорий: $count"
```
10. **Автоматизация задачи обновления системы:**
    Напишите скрипт, который будет проверять наличие обновлений системы и, если они доступны, автоматически устанавливать их.
```
echo "Обновление системы началось: $(date)" >> /var/log/update_system.log

sudo apt update && sudo apt upgrade -y >> /var/log/update_system.log

echo "Обновление системы завершено: $(date)" >> /var/log/update_system.log
```


