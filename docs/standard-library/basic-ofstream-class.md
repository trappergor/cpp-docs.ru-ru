---
title: "Класс basic_ofstream | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::basic_ofstream"
  - "basic_ofstream"
  - "std.basic_ofstream"
  - "fstream/std::basic_ofstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ofstream - класс"
ms.assetid: 3bcc9c51-6dfc-4844-8fcc-22ef57c9dff1
caps.latest.revision: 24
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс basic_ofstream
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\> с элементами типа `Elem`, признаки символов которых определяются классом `Tr`.  
  
## Синтаксис  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_ofstream : public basic_ostream<Elem, Tr>  
```  
  
#### Параметры  
 `Elem`  
 Базовый элемент буфера файла.  
  
 `Tr`  
 Признаки базового элемента буфера файла \(обычно `char_traits`\<`Elem`\>\).  
  
## Заметки  
 Если файл открыт в текстовом режиме, то при записи специализации `wchar_t` `basic_ofstream` в файл будет записана последовательность MBCS.  Внутреннее представление будет использовать буфер символов `wchar_t`.  
  
 Этот объект хранит объект класса `basic_filebuf`\<`Elem`, `Tr`\>.  
  
## Пример  
 В следующем примере показано создание объекта `basic_ofstream` и запись в него текста.  
  
```  
// basic_ofstream_class.cpp  
// compile with: /EHsc  
#include <fstream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ofstream ofs("ofstream.txt");  
    if (!ofs.bad())  
    {  
        ofs << "Writing to a basic_ofstream object..." << endl;  
        ofs.close();  
    }  
}  
```  
  
### Конструкторы  
  
|||  
|-|-|  
|[basic\_ofstream](../Topic/basic_ofstream::basic_ofstream.md)|Создает объект типа `basic_ofstream`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[закрыть](../Topic/basic_ofstream::close.md)|Закрывает файл.|  
|[is\_open](../Topic/basic_ofstream::is_open.md)|Определяет, открыт ли файл.|  
|[open](../Topic/basic_ofstream::open.md)|Открывает файл.|  
|[rdbuf](../Topic/basic_ofstream::rdbuf.md)|Возвращает адрес сохраненного буфера потока.|  
|[swap](../Topic/basic_ofstream::swap.md)|Меняет местами содержимое этого объекта `basic_ofstream` с содержимым указанного объекта `basic_ofstream`.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator \=](../Topic/basic_ofstream::operator=.md)|Назначает содержимое этого объекта потока.  Это назначение перемещения, включающее `rvalue reference`, которое не оставляет копию.|  
  
## Требования  
 **Заголовок:** \<fstream\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Класс basic\_ostream](../Topic/basic_ostream%20Class.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)