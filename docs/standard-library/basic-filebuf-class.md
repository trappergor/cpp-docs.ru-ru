---
title: "Класс basic_filebuf | Microsoft Docs"
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
  - "std.basic_filebuf"
  - "fstream/std::basic_filebuf"
  - "std::basic_filebuf"
  - "basic_filebuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_filebuf - класс"
ms.assetid: 3196ba5c-bf38-41bd-9a95-70323ddfca1a
caps.latest.revision: 24
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс basic_filebuf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает буфер потока, который управляет передачей элементов типа `Elem`, признаки символов которого определяются с помощью класса `Tr`, в последовательность элементов, сохраненную во внешнем файле, и из нее.  
  
## Синтаксис  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_filebuf : public basic_streambuf<Elem, Tr>  
```  
  
#### Параметры  
 `Elem`  
 Базовый элемент буфера файла.  
  
 `Tr`  
 Признаки базового элемента буфера файла \(обычно `char_traits`\<`Elem`\>\).  
  
## Заметки  
 Класс шаблона описывает буфер потока, который управляет передачей элементов типа `Elem`, признаки символов которого определяются с помощью класса `Tr`, в последовательность элементов, сохраненную во внешнем файле, и из нее.  
  
> [!NOTE]
>  Объекты типа `basic_filebuf` создаются с внутренним буфером типа `char *` независимо от `char_type`, заданного параметром типа `Elem`.  Это означает, что строка в Юникоде \(количество символов: `wchar_t`\) будет преобразована в строку ANSI \(количество символов: `char`\) перед записью во внутренний буфер.  Для хранения строк в Юникоде в буфере создайте новый буфер типа `wchar_t` и задайте его с помощью метода [basic\_streambuf::pubsetbuf](../Topic/basic_streambuf::pubsetbuf.md)`()`.  Ниже приведен пример, демонстрирующий такие действия.  
  
 Объект класса `basic_filebuf`\<`Elem`, `Tr`\> сохраняет указатель файла, который определяет объект `FILE`, управляющий потоком, связанным с открытым файлом.  Он также содержит указатели на два аспекта преобразования файла для использования защищенными функциями\-членами [overflow](../Topic/basic_filebuf::overflow.md) и [underflow](../Topic/basic_filebuf::underflow.md).  Дополнительные сведения см. в статье [basic\_filebuf::open](../Topic/basic_filebuf::open.md).  
  
## Пример  
 Следующий пример демонстрирует способ использования объекта типа `basic_filebuf<wchar_t>` для хранения символов Юникода в своем внутреннем буфере, с помощью метода `pubsetbuf()`.  
  
```  
// unicode_basic_filebuf.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string>  
#include <fstream>  
#include <iomanip>  
#include <memory.h>  
#include <string.h>  
  
#define IBUFSIZE 16  
  
using namespace std;  
  
void hexdump(const string& filename);  
  
int main()  
{  
    wchar_t* wszHello = L"Hello World";  
    wchar_t wBuffer[128];  
  
    basic_filebuf<wchar_t> wOutFile;  
  
    // Open a file, wcHello.txt, then write to it, then dump the  
    // file's contents in hex  
    wOutFile.open("wcHello.txt",  
        ios_base::out | ios_base::trunc | ios_base::binary);  
    if(!wOutFile.is_open())  
    {  
        cout << "Error Opening wcHello.txt\n";  
        return -1;  
    }  
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));  
    wOutFile.close();  
    cout << "Hex Dump of wcHello.txt - note that output is ANSI chars:\n";  
    hexdump(string("wcHello.txt"));  
  
    // Open a file, wwHello.txt, then set the internal buffer of  
    // the basic_filebuf object to be of type wchar_t, then write  
    // to the file and dump the file's contents in hex  
    wOutFile.open("wwHello.txt",  
        ios_base::out | ios_base::trunc | ios_base::binary);  
    if(!wOutFile.is_open())  
    {  
        cout << "Error Opening wwHello.txt\n";  
        return -1;  
    }  
    wOutFile.pubsetbuf(wBuffer, (streamsize)128);  
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));  
    wOutFile.close();  
    cout << "\nHex Dump of wwHello.txt - note that output is wchar_t chars:\n";  
    hexdump(string("wwHello.txt"));  
  
    return 0;  
}  
  
// dump contents of filename to stdout in hex  
void hexdump(const string& filename)  
{  
    fstream ifile(filename.c_str(),  
        ios_base::in | ios_base::binary);  
    char *ibuff = new char[IBUFSIZE];  
    char *obuff = new char[(IBUFSIZE*2)+1];  
    int i;  
  
    if(!ifile.is_open())  
    {  
        cout << "Cannot Open " << filename.c_str()  
             << " for reading\n";  
        return;  
    }  
    if(!ibuff || !obuff)  
    {  
        cout << "Cannot Allocate buffers\n";  
        ifile.close();  
        return;  
    }  
  
    while(!ifile.eof())  
    {  
        memset(obuff,0,(IBUFSIZE*2)+1);  
        memset(ibuff,0,IBUFSIZE);  
        ifile.read(ibuff,IBUFSIZE);  
  
        // corner case where file is exactly a multiple of  
        // 16 bytes in length  
        if(ibuff[0] == 0 && ifile.eof())  
            break;  
  
        for(i = 0; i < IBUFSIZE; i++)  
        {  
            if(ibuff[i] >= ' ')  
                obuff[i] = ibuff[i];  
            else  
                obuff[i] = '.';  
  
            cout << setfill('0') << setw(2) << hex  
                 << (int)ibuff[i] << ' ';  
        }  
        cout << "  " << obuff << endl;  
    }  
    ifile.close();  
}  
```  
  
  **Шестнадцатеричный дамп wcHello.txt \(обратите внимание, что на выходе — символы ANSI\):**  
**48 65 6c 6c 6f 20 57 6f 72 6c 64 00 00 00 00 00   Hello World.....  Шестнадцатеричный дамп wwHello.txt \(обратите внимание, что на выходе — символы wchar\_t\):**  
**48 00 65 00 6c 00 6c 00 6f 00 20 00 57 00 6f 00   H.e.l.l.o.  .W.o.  72 00 6c 00 64 00 00 00 00 00 00 00 00 00 00 00   r.l.d...........**    
### Конструкторы  
  
|||  
|-|-|  
|[basic\_filebuf](../Topic/basic_filebuf::basic_filebuf.md)|Создает объект типа `basic_filebuf`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/basic_filebuf::char_type.md)|Связывает имя типа с параметром шаблона `Elem`.|  
|[int\_type](../Topic/basic_filebuf::int_type.md)|Делает этот тип в области `basic_filebuf` эквивалентным типу с таким же именем в области `Tr`.|  
|[off\_type](../Topic/basic_filebuf::off_type.md)|Делает этот тип в области `basic_filebuf` эквивалентным типу с таким же именем в области `Tr`.|  
|[pos\_type](../Topic/basic_filebuf::pos_type.md)|Делает этот тип в области `basic_filebuf` эквивалентным типу с таким же именем в области `Tr`.|  
|[traits\_type](../Topic/basic_filebuf::traits_type.md)|Связывает имя типа с параметром шаблона `Tr`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[закрыть](../Topic/basic_filebuf::close.md)|Закрывает файл.|  
|[is\_open](../Topic/basic_filebuf::is_open.md)|Указывает, открыт ли файл.|  
|[open](../Topic/basic_filebuf::open.md)|Открывает файл.|  
|[переполнение](../Topic/basic_filebuf::overflow.md)|Защищенная виртуальная функция, которая может вызываться при вставке нового символа в полный буфер.|  
|[pbackfail](../Topic/basic_filebuf::pbackfail.md)|Защищенная виртуальная функция\-член пытается поместить элемент обратно во входной поток, затем делает его текущим \(на него указывает следующий указатель\).|  
|[seekoff](../Topic/basic_filebuf::seekoff.md)|Защищенная виртуальная функция\-член пытается изменить текущие положения управляемых потоков.|  
|[seekpos](../Topic/basic_filebuf::seekpos.md)|Защищенная виртуальная функция\-член пытается изменить текущие положения управляемых потоков.|  
|[setbuf](../Topic/basic_filebuf::setbuf.md)|Защищенная виртуальная функция\-член выполняет операции, относящиеся непосредственно к каждому производному буферу потока.|  
|[Swap](../Topic/basic_filebuf::swap.md)|Меняет местами содержимое этого `basic_filebuf` и содержимое указанного параметра `basic_filebuf`.|  
|[sync](../Topic/basic_filebuf::sync.md)|Защищенная виртуальная функция пытается синхронизировать управляемые потоки с любыми связанными внешними потоками.|  
|[uflow](../Topic/basic_streambuf::uflow.md)|Защищенная виртуальная функция для извлечения текущего элемента из входного потока.|  
|[underflow](../Topic/basic_filebuf::underflow.md)|Защищенная виртуальная функция для извлечения текущего элемента из входного потока.|  
  
## Требования  
 **Заголовок:** \<fstream\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<fstream\>](../standard-library/fstream.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)