---
title: "Класс basic_ifstream | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- basic_ifstream
- fstream/std::basic_ifstream
- fstream/std::basic_ifstream::close
- fstream/std::basic_ifstream::is_open
- fstream/std::basic_ifstream::open
- fstream/std::basic_ifstream::rdbuf
- fstream/std::basic_ifstream::swap
dev_langs:
- C++
helpviewer_keywords:
- basic_ifstream class
ms.assetid: 366cd9a7-efc4-4b7f-ba10-c8271e47ffcf
caps.latest.revision: 23
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
ms.openlocfilehash: e1027f916c8ab40a8e1040c3e1da47e5c15a3ae1
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="basicifstream-class"></a>Класс basic_ifstream
Описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> с элементами типа `Elem`, признаки символов которых определяются классом `Tr`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_ifstream : public basic_istream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Параметры  
 `Elem`  
 Базовый элемент буфера файла.  
  
 `Tr`  
 Признаки базового элемента буфера файла (обычно `char_traits`< `Elem`>).  
  
## <a name="remarks"></a>Примечания  
 Объект сохраняет объект класса `basic_filebuf`< `Elem`, `Tr`>.  
  
## <a name="example"></a>Пример  
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
  
## <a name="input-basicifstreamclasstxt"></a>Входные данные: basic_ifstream_class.txt  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
## <a name="output"></a>Вывод  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[basic_ifstream](#basic_ifstream)|Выполняет инициализацию нового экземпляра объекта `basic_ifstream`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[close](#close)|Закрывает файл.|  
|[is_open](#is_open)|Определяет, открыт ли файл.|  
|[open](#open)|Открывает файл.|  
|[rdbuf](#rdbuf)|Возвращает адрес сохраненного буфера потока.|  
|[swap](#swap)|Меняет местами содержимое этого `basic_ifstream` и содержимое указанного параметра `basic_ifstream`.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор=](#op_eq)|Назначает содержимое этого объекта потока. Это назначение перемещения, включающее `rvalue`, которое не оставляет копию.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<fstream>  
  
 **Пространство имен:** std  
  
##  <a name="basic_ifstream"></a>  basic_ifstream::basic_ifstream  
 Создает объект типа `basic_ifstream`.  
  
```  
basic_ifstream();

explicit basic_ifstream(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in,  
    int _Prot = (int)ios_base::_Openprot);

explicit basic_ifstream(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in,  
    int _Prot = (int)ios_base::_Openprot);

basic_ifstream(basic_ifstream&& right);
```  
  
### <a name="parameters"></a>Параметры  
 `_Filename`  
 Имя файла, который необходимо открыть.  
  
 `_Mode`  
 Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `_Prot`  
 Защита открытия файла по умолчанию, эквивалент параметра `shflag` в [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует базовый класс путем вызова [basic_istream](../standard-library/basic-istream-class.md)( `sb`), где `sb` — сохраненный объект класса [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>. Он также инициализирует `sb` путем вызова `basic_filebuf`< `Elem`, `Tr`>.  
  
 Второй и третий конструкторы инициализируют базовый класс путем вызова `basic_istream`( `sb`). Он также инициализирует `sb` путем вызова [basic_filebuf](../standard-library/basic-filebuf-class.md#basic_filebuf)< `Elem`, `Tr`>, затем `sb`. [open](../standard-library/basic-filebuf-class.md#open)( `_Filename`, `_Mode` &#124; `ios_base::in`). Если последняя функция возвращает пустой указатель, конструктор вызывает **setstate**( `failbit`).  
  
 Четвертый конструктор инициализирует объект с содержимым `right`, что рассматривается как ссылка rvalue.  
  
### <a name="example"></a>Пример  
  В следующем примере показано, как считать текст из файла. Чтобы создать файл, см. пример для [basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream).  
  
```  
// basic_ifstream_ctor.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ifstream ifs("basic_ifstream_ctor.txt");  
    if (!ifs.bad())  
    {  
        // Dump the contents of the file to cout.  
        cout << ifs.rdbuf();  
        ifs.close();  
    }  
}  
```  
  
##  <a name="close"></a>  basic_ifstream::close  
 Закрывает файл.  
  
```  
void close();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывает [rdbuf](#rdbuf)**->** [close](../standard-library/basic-filebuf-class.md#close).  
  
### <a name="example"></a>Пример  
  Пример, в котором используется функция **close**, см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).  
  
##  <a name="is_open"></a>  basic_ifstream::is_open  
 Определяет, открыт ли файл.  
  
```  
bool is_open() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если файл открыт, или **false** в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [rdbuf](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open).  
  
### <a name="example"></a>Пример  
  Пример, в котором используется `is_open`, см. в разделе [basic_filebuf::is_open](../standard-library/basic-filebuf-class.md#is_open).  
  
##  <a name="open"></a>  basic_ifstream::open  
 Открывает файл.  
  
```  
void open(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in,  
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,  
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in,  
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
 Эта функция-член вызывает [rdbuf](#rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode` &#124; **ios_base::in**). Если открытие завершается неудачно, функция вызывает [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**), что может создать исключение ios_base::failure.  
  
### <a name="example"></a>Пример  
  Пример, в котором используется функция **open**, см. в разделе [basic_filebuf::open](../standard-library/basic-filebuf-class.md#open).  
  
##  <a name="op_eq"></a>  basic_ifstream::operator=  
 Назначает содержимое этого объекта потока. Это назначение перемещения, включающее rvalue, которое не оставляет копию.  
  
```  
basic_ifstream& operator=(basic_ifstream&& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Ссылка rvalue на объект `basic_ifstream`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `*this`.  
  
### <a name="remarks"></a>Примечания  
 Оператор-член заменяет содержимое объекта при помощи содержимого `right`, которое обрабатывается как ссылка rvalue. Дополнительные сведения см. в разделе [Значения Lvalue и Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md).  
  
##  <a name="rdbuf"></a>  basic_ifstream::rdbuf  
 Возвращает адрес сохраненного буфера потока.  
  
```  
basic_filebuf<Elem, Tr> *rdbuf() const 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект [basic_filebuf](../standard-library/basic-filebuf-class.md), представляющий буфер сохраненного потока.  
  
### <a name="example"></a>Пример  
  Пример, в котором используется `rdbuf`, см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).  
  
##  <a name="swap"></a>  basic_ifstream::swap  
 Меняет местами содержимое двух объектов `basic_ifstream`.  
  
```  
void swap(basic_ifstream& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Ссылка на другой буфер потока.  
  
### <a name="remarks"></a>Примечания  
 Функция-член меняет местами содержимое этого объекта для содержимого `right`.  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../standard-library/iostream-programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)



