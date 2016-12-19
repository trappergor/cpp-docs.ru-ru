---
title: "Навигация по файловой системе | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: f7cc5f5e-a541-4e00-87c7-a3769ef6096d
caps.latest.revision: 14
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Навигация по файловой системе
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Заголовок \<filesystem\> реализует черновой вариант технической спецификации файловой системы \([ISO\/IEC JTC 1\/SC 22\/WG 21 N4100](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4100.pdf)\), а также имеет типы и функции, позволяющие разрабатывать независимый от платформы код для навигации по файловой системе. Так как он является кроссплатформенным, он содержит API\-интерфейсы, которые не являются релевантными для систем Windows. Например, это означает, что `is_fifo(const path&)` всегда возвращает `false` в Windows. Заголовок основан на черновом варианте технической спецификации, не включенном в стандарт C\+\+17 на момент выпуска Visual Studio 2015 RTM. Его члены находятся в пространстве имен `std::experimental::filesystem::v1`.  
  
## Обзор  
 Используйте API\-интерфейсы \<filesystem\> для выполнения следующих задач:  
  
-   выполнение итерации по файлам и каталогам в указанном пути;  
  
-   получение сведений о файлах, включая время создания, размер, расширение и корневой каталог;  
  
-   составление, разделение и сравнение путей;  
  
-   создание, копирование и удаление каталогов;  
  
-   копирование и удаление файлов.  
  
 Дополнительные сведения о вводе\-выводе файлов с помощью стандартной библиотеки см. в разделе [Программирование iostream](../Topic/iostream%20Programming.md).  
  
## Пути  
  
### Создание и составление путей  
 Пути в Windows \(начиная с XP\) изначально хранятся в Юникоде. Класс [path](../Topic/path%20Class%20\(C++%20Standard%20Template%20Library\).md) автоматически выполняет все необходимые преобразования строк. Он принимает аргументы массивов широких и узких символов, а также типы `std::string` и `std::wstring` в формате UTF8 или UTF16. Класс `path` также автоматически нормализует разделители путей. В аргументах конструктора в качестве разделителя каталогов можно использовать одиночную косую черту. Это позволяет применять одинаковые строки для хранения путей в средах Windows и UNIX:  
  
```cpp  
path pathToDisplay(L"/FileSystemTest/SubDir3"); // OK! path pathToDisplay2(L"\\FileSystemTest\\SubDir3"); // Still OK as always path pathToDisplay3(LR"(\FileSystemTest\SubDir3)"); // Raw string literals are OK, too.  
```  
  
 Для объединения двух путей можно использовать перегруженные операторы  `/` и `/=`, которые аналогичны операторам `+` и `+=` в `std::string` и `std::wstring`. Объект `path` будет удобным образом передавать разделители, если вы сами этого не сделали.  
  
```cpp  
path myRoot("C:/FileSystemTest"); // no trailing separator, no problem! myRoot /= path("SubDirRoot"); // C:/FileSystemTest/SubDirRoot  
```  
  
### Проверка путей  
 Класс пути содержит несколько методов, которые возвращают сведения о различных путях для самого пути, в отличие от сущности файловой системы, на которую он может ссылаться. Можно получить корень, относительный путь, имя файла, расширение файла и другие сведения. Можно выполнять итерацию по объекту path для проверки всех папок в иерархии. В следующем примере показано, как выполнять итерацию по пути \(не по каталогу, на который он ссылается\) и получать сведения о его частях.  
  
```cpp  
  
#include <string> #include <iostream> #include <sstream> #include <filesystem> using namespace std; using namespace std::experimental::filesystem::v1; wstring  DisplayPathInfo() { // This path may or may not refer to an existing file. We are // examining this path string, not file system objects. path pathToDisplay(L"C:/FileSystemTest/SubDir3/SubDirLevel2/File2.txt "); wostringstream wos; int i = 0; wos << L"Displaying path info for: " << pathToDisplay << endl; for (path::iterator itr = pathToDisplay.begin(); itr != pathToDisplay.end(); ++itr) { wos << L"path part: " << i++ << L" = " << *itr << endl; } wos << L"root_name() = " << pathToDisplay.root_name() << endl << L"root_path() = " << pathToDisplay.root_path() << endl << L"relative_path() = " << pathToDisplay.relative_path() << endl << L"parent_path() = " << pathToDisplay.parent_path() << endl << L"filename() = " << pathToDisplay.filename() << endl << L"stem() = " << pathToDisplay.stem() << endl << L"extension() = " << pathToDisplay.extension() << endl; return wos.str(); } void main(int argc, char* argv[]) { wcout << DisplayPathInfo() << endl; // wcout << ComparePaths() << endl; // see following example wcout << endl << L"Press Enter to exit" << endl; wstring input; getline(wcin, input); }  
```  
  
 Код создает следующие выходные данные:  
  
```cpp  
Displaying path info for: C:\FileSystemTest\SubDir3\SubDirLevel2\File2.txt path part: 0 = C: path part: 1 = \ path part: 2 = FileSystemTest path part: 3 = SubDir3 path part: 4 = SubDirLevel2 path part: 5 = File2.txt root_name() = C: root_path() = C:\ relative_path() = FileSystemTest\SubDir3\SubDirLevel2\File2.txt parent_path() = C:\FileSystemTest\SubDir3\SubDirLevel2 filename() = File2.txt stem() = File2 extension() = .txt  
```  
  
### Сравнение путей  
 Класс `path` перегружает операторы сравнения на равенство как `std::string` и `std::wstring`. При сравнении двух путей строгое сравнение строк выполняется после нормализации разделителей. Если заключительная косая черта \(или обратная косая черта\) отсутствует, она не добавляется, и это влияет на результат сравнения. В следующем примере показано, как выполняется сравнение значений пути:  
  
```cpp  
  
wstring ComparePaths() { path p0(L"C:/Documents"); // no trailing separator path p1(L"C:/Documents/"); //p0 < p1 path p2(L"C:/Documents/2013/"); // p1 < p2 path p3(L"C:/Documents/2013/Reports/"); // p2 < p3 path p4(L"C:/Documents/2014/");  // p3 < p4 path p5(L"D:/Documents/2013/Reports/"); // p4 < p5 wostringstream wos; wos << boolalpha << p0.wstring() << L" < " << p1.wstring() << L": " << (p0 < p1) << endl << p1.wstring() << L" < " << p2.wstring() << L": " << (p1 < p2) << endl << p2.wstring() << L" < " << p3.wstring() << L": " << (p2 < p3) << endl << p3.wstring() << L" < " << p4.wstring() << L": " << (p3 < p4) << endl << p4.wstring() << L" < " << p5.wstring() << L": " << (p4 < p5) << endl; return wos.str(); } /* Output: C:\Documents < C:\Documents\: true C:\Documents\ < C:\Documents\2013\: true C:\Documents\2013\ < C:\Documents\2013\Reports\: true C:\Documents\2013\Reports\ < C:\Documents\2014\: true C:\Documents\2014\ < D:\Documents\2013\Reports\: true */  
```  
  
 Для запуска этого кода вставьте его в полный пример выше и раскомментируйте строку, которая вызывает его в основном объекте.  
  
### Преобразование между типами пути и строки  
 Объект `path` может быть неявно преобразован в `std::wstring` или `std::string`. Это означает, что путь можно передать в функции, например в [wofstream::open](../Topic/basic_ofstream::open.md), как показано в следующем примере:  
  
```cpp  
wchar_t* p = L"C:/test"; path filePath(p); filePath /= L"NewFile.txt"; // Open, write to, and close the file. wofstream myFile; myFile.open(filePath); myFile << L"Lorem ipsum..."; myFile.close  
  
```  
  
## Итерация по каталогам и файлам  
 Заголовок \<filesystem\> предоставляет тип [directory\_iterator](../Topic/directory_iterator%20Class.md) для выполнения итерации по одиночным каталогам, а также класс [recursive\_directory\_iterator](../Topic/recursive_directory_iterator%20Class.md) для рекурсивного выполнения итерации по каталогу и его подкаталогам. После создания итератора путем передачи ему объекта `path` итератор указывает на первое значение directory\_entry в пути. Создайте конечный итератор путем вызова конструктора по умолчанию.  
  
 При проходе по каталогу можно обнаружить элементы нескольких типов, включая каталоги, файлы, символические ссылки и файлы сокетов, но не ограничиваясь ими.`directory_iterator` возвращает элементы в виде объектов [directory\_entry](../standard-library/directory-entry-class.md), и каждый объект имеет элемент [status\(\)](http://msdn.microsoft.com/ru-ru/a70a3c55-3a76-417f-abaf-862ff94b2056), который указывает, какого типа записи вы видите. В ходе проверки этого значения можно принять решение о том, что делать для любой конкретной записи. В следующем примере выполняется проход через один каталог, и если запись в каталоге является обычным файлом, то код выводит некоторые сведения об этом файле. Если запись является каталогом, то отображается только имя.  
  
```cpp  
#include <string> #include <iostream> #include <iomanip> #include <filesystem> #include <chrono> #include <time.h> using namespace std; using namespace std::experimental::filesystem::v1; // Display the last write time for the file wstring LastWriteTimeToLocalTime(const path& file_path) { const auto last = chrono::system_clock::to_time_t(last_write_time(file_path)); tm timeinfo; localtime_s(&timeinfo, &last); wchar_t buf[56]; _wasctime_s(buf, 56, &timeinfo); // appends '\n' return wstring{ buf }; } // List files and directories in the specified path void DisplayFolderContents(const path& p) { wcout << L"Begin iterating " << p.wstring() << endl; for (const auto& entry : directory_iterator{ p }) { if (is_regular_file(entry.status())) { wcout << L" File: " << entry.path().filename() << " : " << LastWriteTimeToLocalTime(entry.path()); } else if (is_directory(entry.status())) { wcout << L" Dir: " << entry.path().filename() << endl; } } } void main() { wstring dir{ LR"(C:\users\public\documents\)" }; path p{ dir }; if (!is_directory(p)) { wcout << L"No such directory: " << dir << endl; return; } DisplayFolderContents(p); // IterateFolderRecursively(p); // see example wcout << endl << L"Press Enter to exit" << endl; wstring input; getline(wcin, input); }  
```  
  
### Рекурсивная итерация по дереву каталогов  
 В следующем примере показано, как выполнять рекурсивную итерацию по дереву каталогов. Для запуска этой функции вставьте ее в предыдущий пример кода после функции DisplayFolderContents и раскомментируйте строку, которая вызывает ее в основном объекте.  
  
```cpp  
// List files and directories recursively in the path void IterateFolderRecursively(const path& p) { wcout << L"Begin iterating " << p.wstring() << " recursively" << endl; for (recursive_directory_iterator it{ p }, end; it != end; ++it) { if (is_regular_file(it->status())) { wcout << setw(it.depth()) << L" " << L"File: " << it->path().filename() << L" : " << LastWriteTimeToLocalTime(it->path()); } else if (is_directory(it->status())) { wcout << setw(it.depth()) << L" " << L"Dir: " << it->path().filename() << endl; } } }  
```  
  
### Обработка символических ссылок  
 Обнаружение символических ссылок еще не поддерживается в Visual C\+\+ для Visual Studio 2015.