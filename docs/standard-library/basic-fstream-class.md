---
title: "Класс basic_fstream | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- basic_fstream
- fstream/std::basic_fstream
- fstream/std::basic_fstream::close
- fstream/std::basic_fstream::is_open
- fstream/std::basic_fstream::open
- fstream/std::basic_fstream::rdbuf
- fstream/std::basic_fstream::swap
dev_langs:
- C++
helpviewer_keywords:
- basic_fstream class
ms.assetid: 8473817e-42a4-430b-82b8-b476c86bcf8a
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: f9d52128703d021ba3a880ff899ca71b144e89ec
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="basicfstream-class"></a>Класс basic_fstream
Описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> с элементами типа `Elem`, признаки символов которых определяются классом `Tr`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_fstream : public basic_iostream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Параметры  
 `Elem`  
 Базовый элемент буфера файла.  
  
 `Tr`  
 Признаки базового элемента буфера файла (обычно `char_traits`< `Elem`>).  
  
## <a name="remarks"></a>Примечания  
 Объект сохраняет объект класса `basic_filebuf`< `Elem`, `Tr`>.  
  
> [!NOTE]
>  Указатель get и указатель put объекта fstream **ЗАВИСЯТ** друг от друга. При перемещении указателя get указатель put также перемещается.  
  
## <a name="example"></a>Пример  
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
  
```Output  
Writing to a basic_fstream object...  
```  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[basic_fstream](#basic_fstream)|Создает объект типа `basic_fstream`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[close](#close)|Закрывает файл.|  
|[is_open](#is_open)|Определяет, открыт ли файл.|  
|[open](#open)|Открывает файл.|  
|[rdbuf](#rdbuf)|Возвращает адрес буфера сохраненного потока типа pointer в [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>.|  
|[swap](#swap)|Меняет местами содержимое данного объекта с содержимым другого объекта `basic_fstream`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<fstream>  
  
 **Пространство имен:** std  
  
##  <a name="basic_fstream"></a>  basic_fstream::basic_fstream  
 Создает объект типа `basic_fstream`.  
  
```  
basic_fstream();

explicit basic_fstream(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

explicit basic_fstream(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

basic_fstream(basic_fstream&& right);
```  
  
### <a name="parameters"></a>Параметры  
 `_Filename`  
 Имя файла, который необходимо открыть.  
  
 `_Mode`  
 Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `_Prot`  
 Защита открытия файла по умолчанию, эквивалент параметра `shflag` в [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует базовый класс путем вызова [basic_iostream](../standard-library/basic-iostream-class.md)( **sb**), где **sb** — сохраненный объект класса [basic_filebuf](../standard-library/basic-filebuf-class.md) \< **Elem**, **Tr**>. Он также инициализирует **sb** путем вызова `basic_filebuf`\< **Elem**, **Tr**.  
  
 Второй и третий конструкторы инициализируют базовый класс путем вызова `basic_iostream`( **sb**). Он также инициализирует **sb** путем вызова `basic_filebuf`\< **Elem**, **Tr**>, затем **sb.**[open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode`). Если последняя функция возвращает пустой указатель, конструктор вызывает [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**).  
  
 Четвертый конструктор инициализирует объект с содержимым `right`, что рассматривается как ссылка rvalue.  
  
### <a name="example"></a>Пример  
  Пример использования `basic_fstream` см. в разделе [streampos](../standard-library/ios-typedefs.md#streampos).  
  
##  <a name="close"></a>  basic_fstream::close  
 Закрывает файл.  
  
```  
void close();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывает [rdbuf](#rdbuf)**->** [close](../standard-library/basic-filebuf-class.md#close).  
  
### <a name="example"></a>Пример  
  Пример использования **close** см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).  
  
##  <a name="is_open"></a>  basic_fstream::is_open  
 Определяет, открыт ли файл.  
  
```  
bool is_open() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если файл открыт, или **false** в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [rdbuf](#rdbuf)**->**[is_open](../standard-library/basic-filebuf-class.md#is_open).  
  
### <a name="example"></a>Пример  
  Пример использования `is_open` см. в разделе [basic_filebuf::is_open](../standard-library/basic-filebuf-class.md#is_open).  
  
##  <a name="open"></a>  basic_fstream::open  
 Открывает файл.  
  
```  
void open(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,  
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

void open(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode);
```  
  
### <a name="parameters"></a>Параметры  
 `_Filename`  
 Имя файла, который необходимо открыть.  
  
 `_Mode`  
 Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `_Prot`  
 Защита открытия файла по умолчанию, эквивалент параметра `shflag` в [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывает [rdbuf](#rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode`). Если эта функция возвращает пустой указатель, конструктор вызывает [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**).  
  
### <a name="example"></a>Пример  
  Пример использования **open** см. в разделе [basic_filebuf::open](../standard-library/basic-filebuf-class.md#open).  
  
##  <a name="op_eq"></a>  basic_fstream::operator=  
 Назначает этому объекту содержимое из указанного объекта потока. Это назначение перемещения с использованием rvalue, после которого не остается копии.  
  
```  
basic_fstream& operator=(basic_fstream&& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Ссылка lvalue на объект `basic_fstream`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `*this`.  
  
### <a name="remarks"></a>Примечания  
 Оператор-член заменяет содержимое объекта при помощи содержимого `right`, которое обрабатывается как ссылка rvalue.  
  
##  <a name="rdbuf"></a>  basic_fstream::rdbuf  
 Возвращает адрес буфера сохраненного потока типа pointer в [basic_filebuf](../standard-library/basic-filebuf-class.md)\< **Elem**, **Tr**>.  
  
```  
basic_filebuf<Elem, Tr> *rdbuf() const 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Адрес сохраненного буфера потока.  
  
### <a name="example"></a>Пример  
  Пример использования `rdbuf` см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).  
  
##  <a name="swap"></a>  basic_fstream::swap  
 Меняет местами содержимое двух объектов `basic_fstream`.  
  
```  
void swap(basic_fstream& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Ссылка `lvalue` на объект `basic_fstream`.  
  
### <a name="remarks"></a>Примечания  
 Функция-член меняет местами содержимое этого объекта и содержимое `right`.  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../standard-library/iostream-programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)


