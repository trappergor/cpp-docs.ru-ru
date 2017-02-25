---
title: "Класс basic_ifstream | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "basic_ifstream"
  - "fstream/std::basic_ifstream"
  - "std::basic_ifstream"
  - "std.basic_ifstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ifstream - класс"
ms.assetid: 366cd9a7-efc4-4b7f-ba10-c8271e47ffcf
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# Класс basic_ifstream
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\> с элементами типа `Elem`, признаки символов которых определяются классом `Tr`.  
  
## Синтаксис  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_ifstream : public basic_istream<Elem, Tr>  
```  
  
#### Параметры  
 `Elem`  
 Базовый элемент буфера файла.  
  
 `Tr`  
 Признаки базового элемента буфера файла \(обычно `char_traits`\<`Elem`\>\).  
  
## Заметки  
 Этот объект хранит объект класса `basic_filebuf`\<`Elem`, `Tr`\>.  
  
## Пример  
 В следующем примере показано, как считать текст из файла.  
  
```  
// basic_ifstream_class.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ifstream ifs("basic_ifstream_class.txt");  
    if (!ifs.bad())  
    {  
        // Dump the contents of the file to cout.  
        cout << ifs.rdbuf();  
        ifs.close();  
    }  
}  
```  
  
## Входные данные: basic\_ifstream\_class.txt  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
## Вывод  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
### Конструкторы  
  
|||  
|-|-|  
|[basic\_ifstream](../Topic/basic_ifstream::basic_ifstream.md)|Выполняет инициализацию нового экземпляра объекта `basic_ifstream`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[закрыть](../Topic/basic_ifstream::close.md)|Закрывает файл.|  
|[is\_open](../Topic/basic_ifstream::is_open.md)|Определяет, открыт ли файл.|  
|[open](../Topic/basic_ifstream::open.md)|Открывает файл.|  
|[rdbuf](../Topic/basic_ifstream::rdbuf.md)|Возвращает адрес сохраненного буфера потока.|  
|[swap](../Topic/basic_ifstream::swap.md)|Меняет местами содержимое этого `basic_ifstream` и содержимое указанного параметра `basic_ifstream`.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator \=](../Topic/basic_ifstream::operator=.md)|Назначает содержимое этого объекта потока.  Это назначение перемещения, включающее `rvalue`, которое не оставляет копию.|  
  
## Требования  
 **Заголовок:** \<fstream\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)