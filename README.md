## **Python Module**

> ###### **Check File Exists**

```

def check_file_exists(curdir, name_file, size_file):
    # The function goes through the files in the current folder
    for root, dirs, files in os.walk(curdir):
        for file in files:
            print(file)
            # if the name is in the files and if this file exists and is not equal to !=0
            if name_file in file:
                if os.path.exists(file) and os.stat(file).st_size != 0:
                    # if the size is less than specified then True if not then False
                    if os.path.getsize(file) < size_file:
                        return True
                    else:
                        return False

curdir = os.path.abspath(os.curdir) + "\\"
check_file_exists(curdir, "ref", 3000000)

```

Rus: Цикл проходится в текущей папке по файлам если имя есть в файлах, и если этот файл существует и не равен !=0, и размер меньше чем указали тогда возвращает True если нет файла или другой размер то False

---

> ###### **Get Path**

```
def getPath(curDir, targetFolder, levelsup):
    os.chdir(curDir)
    for i in range(levelsup):
        if i > 0:
            output = output + "\.."
        else:
            output = ".."
    os.chdir(output)
    targetDir = os.path.abspath(os.getcwd())
    os.chdir(curDir)
    return targetDir + targetFolder


curdir = os.path.abspath(os.getcwd())
getPath(curdir, "\\Daily\\", 1)

```

getPath(curdir, "\\Daily\\", 1)

* curdir - текущая папка
* "\\Daily\\" - путь к какой-то папки

* 1 - уровень выхода из папки

---
