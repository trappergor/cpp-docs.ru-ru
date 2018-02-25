---
title: "Класс basic_istringstream | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- sstream/std::basic_istringstream
- sstream/std::basic_istringstream::allocator_type
- sstream/std::basic_istringstream::rdbuf
- sstream/std::basic_istringstream::str
- sstream/std::basic_istringstream::swap
dev_langs:
- C++
helpviewer_keywords:
- std::basic_istringstream [C++]
- std::basic_istringstream [C++], allocator_type
- std::basic_istringstream [C++], rdbuf
- std::basic_istringstream [C++], str
- std::basic_istringstream [C++], swap
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6956b4708061c5eb18ec2adf1570920980dd17e1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="basicistringstream-class"></a>Класс basic_istringstream
Описывает объект, управляющий извлечением элементов и закодированных объектов из буфера класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>  
class basic_istringstream : public basic_istream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Параметры  
 `Alloc`  
 Класс распределителя.  
  
 `Elem`  
 Тип основного элемента строки.  
  
 *Tr*  
 Признаки символа, соответствующие основному элементу строки.  
  
## <a name="remarks"></a>Примечания  
 Класс шаблона описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> с элементами типа **Elem**, признаки символов которых определяются классом **Tr**, а элементы выделяются распределителем класса `Alloc`. Объект сохраняет объект класса basic_stringbuf< **Elem**, **Tr**, `Alloc`>.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[basic_istringstream](#basic_istringstream)|Создает объект типа `basic_istringstream`.|  
  
### <a name="typedefs"></a>Определения типов  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|Этот тип является синонимом для параметра шаблона `Alloc`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[rdbuf](#rdbuf)|Возвращает адрес буфера сохраненного потока типа `pointer` в [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>.|  
|[str](#str)|Задает или получает текст в буфере строк без изменения позиции записи.|  
|[swap](#swap)|Меняет местами значения в этом объекте `basic_istringstream` и значения предоставленного объекта.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор=](#op_eq)|Назначает значения этому объекту `basic_istringstream` из параметра объекта.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<sstream>  
  
 **Пространство имен:** std  
  
##  <a name="allocator_type"></a>  basic_istringstream::allocator_type  
 Этот тип является синонимом для параметра шаблона `Alloc`.  
  
```  
typedef Alloc allocator_type;  
```  
  
##  <a name="basic_istringstream"></a>  basic_istringstream::basic_istringstream  
 Создает объект типа `basic_istringstream`.  
  
```  
explicit basic_istringstream(
    ios_base::openmode _Mode = ios_base::in);

explicit basic_istringstream(
    const basic_string<Elem, Tr, Alloc>& str,  
    ios_base::openmode _Mode = ios_base::in);

basic_istringstream(
    basic_istringstream&& right);
```  
  
### <a name="parameters"></a>Параметры  
 `_Mode`  
 Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `str`  
 Объект типа `basic_string`.  
  
 `right`  
 Ссылка rvalue на объект `basic_istringstream`.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует базовый класс путем вызова [basic_istream](../standard-library/basic-istream-class.md)( `sb`), где `sb` — сохраненный объект класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>. Он также инициализирует `sb` путем вызова `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `_Mode` &#124; `ios_base::in`).  
  
 Второй конструктор инициализирует базовый класс путем вызова `basic_istream(sb)`. Он также инициализирует `sb` путем вызова `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `str`, `_Mode` &#124; `ios_base::in`).  
  
 Третий конструктор инициализирует объект с содержимым `right`, что рассматривается как ссылка rvalue.  
  
##  <a name="op_eq"></a>  basic_istringstream::operator=  
 Назначает значения этому объекту `basic_istringstream` из параметра объекта.  
  
```  
basic_istringstream& operator=(basic_istringstream&& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Ссылка rvalue на объект `basic_istringstream`.  
  
### <a name="remarks"></a>Примечания  
 Оператор-член заменяет содержимое объекта на содержимое `right`, которое обрабатывается как присваивание перемещением ссылки rvalue.  
  
##  <a name="rdbuf"></a>  basic_istringstream::rdbuf  
 Возвращает адрес буфера сохраненного потока типа **pointer** в [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.  
  
```  
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Адрес буфера сохраненного потока типа **pointer** в basic_stringbuf< **Elem**, **Tr**, `Alloc`>.  
  
### <a name="example"></a>Пример  
  Пример, в котором используется `rdbuf`, см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).  
  
##  <a name="str"></a>  basic_istringstream::str  
 Задает или получает текст в буфере строк без изменения позиции записи.  
  
```  
basic_string<Elem, Tr, Alloc> str() const;

 
void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```  
  
### <a name="parameters"></a>Параметры  
 `_Newstr`  
 Новая строка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает объект класса [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`>, управляемая последовательность которого является копией последовательности, управляемой **\*this**.  
  
### <a name="remarks"></a>Примечания  
 Первая функция-член возвращает [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str). Вторая функция-член вызывает `rdbuf` -> **str**( `_Newstr`).  
  
### <a name="example"></a>Пример  
  Пример использования **str** см. в разделе [basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str).  
  
##  <a name="swap"></a>  basic_istringstream::swap  
 Меняет местами значения двух объектов `basic_istringstream`.  
  
```  
void swap(basic_istringstream& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`right`|Ссылка `lvalue` на объект `basic_istringstream`.|  
  
### <a name="remarks"></a>Примечания  
 Функция-член меняет местами значения этого объекта и значения `right`.  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../standard-library/iostream-programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)

