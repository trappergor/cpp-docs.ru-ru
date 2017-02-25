---
title: "Класс basic_fstream | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::basic_fstream"
  - "basic_fstream"
  - "fstream/std::basic_fstream"
  - "std.basic_fstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_fstream - класс"
ms.assetid: 8473817e-42a4-430b-82b8-b476c86bcf8a
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# Класс basic_fstream
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\> с элементами типа `Elem`, признаки символов которых определяются классом `Tr`.  
  
## Синтаксис  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_fstream : public basic_iostream<Elem, Tr>  
```  
  
#### Параметры  
 `Elem`  
 Базовый элемент буфера файла.  
  
 `Tr`  
 Признаки базового элемента буфера файла \(обычно `char_traits`\<`Elem`\>\).  
  
## Заметки  
 Этот объект сохраняет объект класса `basic_filebuf`\<`Elem`, `Tr`\>.  
  
> [!NOTE]
>  Указатель get и указатель put объекта fstream **ЗАВИСЯТ** друг от друга.  При перемещении указателя get указатель put также перемещается.  
  
## Пример  
 В следующем примере показано, как создать объект `basic_fstream`, из которого можно считать данные и в который можно записать данные.  
  
```  
// basic_fstream_class.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    fstream fs("fstream.txt", ios::in | ios::out | ios::trunc);  
    if (!fs.bad())  
    {  
        // Write to the file.  
        fs << "Writing to a basic_fstream object..." << endl;  
        fs.close();  
  
        // Dump the contents of the file to cout.  
        fs.open("fstream.txt", ios::in);  
        cout << fs.rdbuf();  
        fs.close();  
    }  
}  
```  
  
  **Запись в объект basic\_fstream...**   
### Конструкторы  
  
|||  
|-|-|  
|[basic\_fstream](../Topic/basic_fstream::basic_fstream.md)|Создает объект типа `basic_fstream`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[закрыть](../Topic/basic_fstream::close.md)|Закрывает файл.|  
|[is\_open](../Topic/basic_fstream::is_open.md)|Определяет, открыт ли файл.|  
|[open](../Topic/basic_fstream::open.md)|Открывает файл.|  
|[rdbuf](../Topic/basic_fstream::rdbuf.md)|Возвращает адрес буфера сохраненного потока типа pointer в [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\>.|  
|[swap](../Topic/basic_fstream::swap.md)|Меняет местами содержимое данного объекта с содержимым другого объекта `basic_fstream`.|  
  
## Требования  
 **Заголовок:** \<fstream\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)