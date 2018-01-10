---
title: "Операторы &lt;istream&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: istream/std::operator&gt;&gt;
dev_langs: C++
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a33a333cc9e70ee57cd1d5612e6de008d49b1d72
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ltistreamgt-operators"></a>Операторы &lt;istream&gt;
 
##  <a name="op_gt_gt"></a> operator&gt;&gt;  
 Извлекает символы и строки из потока.  
  
```  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,   
    Elem* str);

template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,   
    Elem& Ch);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    signed char* str);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    signed char& Ch);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    unsigned char* str);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    unsigned char& Ch);

template <class Elem, class Tr, class Type>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,  
    Type& val);
```  
  
### <a name="parameters"></a>Параметры  
 `Ch`  
 Символ.  
  
 `Istr`  
 Поток.  
  
 `str`  
 Строка.  
  
 `val`  
 Тип.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поток.  
  
### <a name="remarks"></a>Примечания  
 Класс `basic_istream` также определяет несколько операторов извлечения. Дополнительные сведения см. в разделе [basic_istream::operator>>](../standard-library/basic-istream-class.md#op_gt_gt).  
  
 Функция-шаблон:  
  
```cpp  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```  
  
 извлекает до *N* − 1 элементов и сохраняет их в массив, начиная с _ *Str*. Если `Istr`. [width](../standard-library/ios-base-class.md#width) больше нуля, *N* имеет значение `Istr`. **width**; в противном случае это будет размер самого большого массива из **Elem**, который может быть объявлен. Функция всегда сохраняет значение **Elem()** после любого извлеченного и сохраненного элемента. Извлечение останавливается досрочно при достижении конца файла, на символе со значением **Elem**(0) (который не извлекается), или на любом элементе (который не извлекается), который будет отклонен [ws](../standard-library/istream-functions.md#ws). Если функция не извлекает ни один элемент, она вызывает `Istr`. [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). В любом случае она вызывает `Istr`. **width**(0) и возвращает `Istr`.  
  
 **Примечание о безопасности.** Заканчивающаяся нулем строка, извлекаемая из входного потока, не должна превышать размер буфера назначения `str`. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 Функция-шаблон:  
  
```cpp  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```  
  
 извлекает элемент, если это возможно, и сохраняет его в `Ch`. В противном случае она вызывает **is**. [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). В любом случае она возвращает `Istr`.  
  
 Функция-шаблон:  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```  
  
 возвращает `Istr` >> (`char`**\***) `str`.  
  
 Функция-шаблон:  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```  
  
 возвращает `Istr` >> (**char&**) `Ch`.  
  
 Функция-шаблон:  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```  
  
 возвращает `Istr` >> (**char \***) `str`.  
  
 Функция-шаблон:  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```  
  
 возвращает `Istr` >> (**char&**) `Ch`.  
  
 Функция-шаблон:  
  
```cpp  
template <class Elem, class Tr, class Type>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,  
    Type& val);
```  
  
 возвращает `Istr` `>>` `val` (и в процессе преобразует `rvalue reference` в `Istr` в `lvalue`).  
  
### <a name="example"></a>Пример  
  
```cpp  
// istream_op_extract.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   ws( cin );  
   char c[10];  
  
   cin.width( 9 );  
   cin >> c;  
   cout << c << endl;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [\<istream>](../standard-library/istream.md)

