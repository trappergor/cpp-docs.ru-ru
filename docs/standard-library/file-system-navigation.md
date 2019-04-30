---
title: Навигация по файловой системе
ms.date: 11/04/2016
ms.assetid: f7cc5f5e-a541-4e00-87c7-a3769ef6096d
ms.openlocfilehash: cfdc789daab5b476566f2072109d23fb9310094f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405200"
---
# <a name="file-system-navigation"></a>Навигация по файловой системе

\<Filesystem > реализует заголовок C++ файл системы технические спецификации ISO/IEC TS 18822: 2015 (окончательный вариант: [ISO/IEC JTC 1/SC 22/WG 21 N4100](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4100.pdf)) и имеет типы и функции, позволяющие писать независимый от платформы код для навигации по файловой системе. Так как он является кроссплатформенным, он содержит API-интерфейсы, которые не являются релевантными для систем Windows. Например, это означает, что `is_fifo(const path&)` всегда возвращает **false** на Windows.

## <a name="overview"></a>Обзор

Используйте API-интерфейсы \<filesystem> для выполнения следующих задач:

- выполнение итерации по файлам и каталогам в указанном пути;

- получение сведений о файлах, включая время создания, размер, расширение и корневой каталог;

- составление, разделение и сравнение путей;

- создание, копирование и удаление каталогов;

- копирование и удаление файлов.

Дополнительные сведения о вводе-выводе файлов с помощью стандартной библиотеки см. в разделе [Программирование iostream](../standard-library/iostream-programming.md).

## <a name="paths"></a>Пути

### <a name="constructing-and-composing-paths"></a>Создание и составление путей

Пути в Windows (начиная с XP) изначально хранятся в Юникоде. Класс [path](../standard-library/path-class.md) автоматически выполняет все необходимые преобразования строк. Он принимает аргументы массивов широких и узких символов, а также типы `std::string` и `std::wstring` в формате UTF8 или UTF16. Класс `path` также автоматически нормализует разделители путей. В аргументах конструктора в качестве разделителя каталогов можно использовать одиночную косую черту. Это позволяет применять одинаковые строки для хранения путей в средах Windows и UNIX:

```cpp
path pathToDisplay(L"/FileSystemTest/SubDir3");     // OK!
path pathToDisplay2(L"\\FileSystemTest\\SubDir3");  // Still OK as always
path pathToDisplay3(LR"(\FileSystemTest\SubDir3)"); // Raw string literals are OK, too.
```

Для объединения двух путей можно использовать перегруженные операторы `/` и `/=` , которые аналогичны операторам `+` и `+=` в `std::string` и `std::wstring`. Объект `path` будет удобным образом передавать разделители, если вы сами этого не сделали.

```cpp
path myRoot("C:/FileSystemTest");  // no trailing separator, no problem!
myRoot /= path("SubDirRoot");      // C:/FileSystemTest/SubDirRoot
```

### <a name="examining-paths"></a>Проверка путей

Класс пути содержит несколько методов, которые возвращают сведения о различных путях для самого пути, в отличие от сущности файловой системы, на которую он может ссылаться. Можно получить корень, относительный путь, имя файла, расширение файла и другие сведения. Можно выполнять итерацию по объекту path для проверки всех папок в иерархии. В следующем примере показано, как выполнять итерацию по пути (не по каталогу, на который он ссылается) и получать сведения о его частях.

```cpp
// filesystem_path_example.cpp
// compile by using: /EHsc
#include <string>
#include <iostream>
#include <sstream>
#include <filesystem>

using namespace std;
using namespace std::experimental::filesystem;

wstring DisplayPathInfo()
{
    // This path may or may not refer to an existing file. We are
    // examining this path string, not file system objects.
    path pathToDisplay(L"C:/FileSystemTest/SubDir3/SubDirLevel2/File2.txt ");

    wostringstream wos;
    int i = 0;
    wos << L"Displaying path info for: " << pathToDisplay << endl;
    for (path::iterator itr = pathToDisplay.begin(); itr != pathToDisplay.end(); ++itr)
    {
        wos << L"path part: " << i++ << L" = " << *itr << endl;
    }

    wos << L"root_name() = " << pathToDisplay.root_name() << endl
        << L"root_path() = " << pathToDisplay.root_path() << endl
        << L"relative_path() = " << pathToDisplay.relative_path() << endl
        << L"parent_path() = " << pathToDisplay.parent_path() << endl
        << L"filename() = " << pathToDisplay.filename() << endl
        << L"stem() = " << pathToDisplay.stem() << endl
        << L"extension() = " << pathToDisplay.extension() << endl;

    return wos.str();
}

void main(int argc, char* argv[])
{
    wcout << DisplayPathInfo() << endl;
    // wcout << ComparePaths() << endl; // see following example
    wcout << endl << L"Press Enter to exit" << endl;
    wstring input;
    getline(wcin, input);
}
```

Код создает следующие выходные данные:

```Output
Displaying path info for: C:\FileSystemTest\SubDir3\SubDirLevel2\File2.txt
path part: 0 = C:
path part: 1 = \
path part: 2 = FileSystemTest
path part: 3 = SubDir3
path part: 4 = SubDirLevel2
path part: 5 = File2.txt
root_name() = C:
root_path() = C:\
relative_path() = FileSystemTest\SubDir3\SubDirLevel2\File2.txt
parent_path() = C:\FileSystemTest\SubDir3\SubDirLevel2
filename() = File2.txt
stem() = File2
extension() = .txt
```

### <a name="comparing-paths"></a>Сравнение путей

Класс `path` перегружает операторы сравнения на равенство как `std::string` и `std::wstring`. При сравнении двух путей строгое сравнение строк выполняется после нормализации разделителей. Если заключительная косая черта (или обратная косая черта) отсутствует, она не добавляется, и это влияет на результат сравнения. В следующем примере показано, как выполняется сравнение значений пути:

```cpp
wstring ComparePaths()
{
    path p0(L"C:/Documents");                 // no trailing separator
    path p1(L"C:/Documents/");                // p0 < p1
    path p2(L"C:/Documents/2013/");           // p1 < p2
    path p3(L"C:/Documents/2013/Reports/");   // p2 < p3
    path p4(L"C:/Documents/2014/");           // p3 < p4
    path p5(L"D:/Documents/2013/Reports/");   // p4 < p5

    wostringstream wos;
    wos << boolalpha <<
        p0.wstring() << L" < " << p1.wstring() << L": " << (p0 < p1) << endl <<
        p1.wstring() << L" < " << p2.wstring() << L": " << (p1 < p2) << endl <<
        p2.wstring() << L" < " << p3.wstring() << L": " << (p2 < p3) << endl <<
        p3.wstring() << L" < " << p4.wstring() << L": " << (p3 < p4) << endl <<
        p4.wstring() << L" < " << p5.wstring() << L": " << (p4 < p5) << endl;
    return wos.str();
}
```

```Output
C:\Documents < C:\Documents\: true
C:\Documents\ < C:\Documents\2013\: true
C:\Documents\2013\ < C:\Documents\2013\Reports\: true
C:\Documents\2013\Reports\ < C:\Documents\2014\: true
C:\Documents\2014\ < D:\Documents\2013\Reports\: true
```

Для запуска этого кода вставьте его в полный пример выше перед `main` и раскомментируйте строку, которая вызывает его в основном объекте.

### <a name="converting-between-path-and-string-types"></a>Преобразование между типами пути и строки

Объект `path` может быть неявно преобразован в `std::wstring` или `std::string`. Это означает, что путь можно передать в функции, например в [wofstream::open](../standard-library/basic-ofstream-class.md#open), как показано в следующем примере:

```cpp
// filesystem_path_conversion.cpp
// compile by using: /EHsc
#include <string>
#include <iostream>
#include <fstream>
#include <filesystem>

using namespace std;
using namespace std::experimental::filesystem;

void main(int argc, char* argv[])
{
    wchar_t* p = L"C:/Users/Public/Documents";
    path filePath(p);

    filePath /= L"NewFile.txt";

    // Open, write to, and close the file.
    wofstream writeFile(filePath, ios::out);  // implicit conversion
    writeFile << L"Lorem ipsum\nDolor sit amet";
    writeFile.close();

    // Open, read, and close the file.
    wifstream readFile;
    wstring line;
    readFile.open(filePath);  // implicit conversions
    wcout << L"File " << filePath << L" contains:" << endl;
    while (readFile.good())
    {
        getline(readFile, line);
        wcout << line << endl;
    }
    readFile.close();

    wcout << endl << L"Press Enter to exit" << endl;
    wstring input;
    getline(wcin, input);
}
```

```Output
File C:\Users\Public\Documents\NewFile.txt contains:
Lorem ipsum
Dolor sit amet

Press Enter to exit
```

## <a name="iterating-directories-and-files"></a>Итерация по каталогам и файлам

Заголовок \<filesystem> предоставляет тип [directory_iterator](../standard-library/directory-iterator-class.md) для выполнения итерации по одиночным каталогам, а также класс [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) для рекурсивного выполнения итерации по каталогу и его подкаталогам. После создания итератора путем передачи ему объекта `path` итератор указывает на первое значение directory_entry в пути. Создайте конечный итератор путем вызова конструктора по умолчанию.

При проходе по каталогу можно обнаружить элементы нескольких типов, включая каталоги, файлы, символические ссылки и файлы сокетов, но не ограничиваясь ими. `directory_iterator` возвращает свои элементы как объекты [directory_entry](../standard-library/directory-entry-class.md).
