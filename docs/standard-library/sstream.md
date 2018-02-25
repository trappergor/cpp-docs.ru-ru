---
title: "&lt;sstream&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <sstream>
dev_langs:
- C++
helpviewer_keywords:
- sstream header
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 319c9cc1b61565eaeffb442b2f4e280aab9b720c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ltsstreamgt"></a>&lt;sstream&gt;
Определяет несколько классов шаблонов, поддерживающих операции iostreams для последовательностей, хранящихся в выделенном массиве объекта. Такие последовательности легко преобразуются в объекты класса шаблонов [basic_string](../standard-library/basic-string-class.md) и из них.  
  
## <a name="syntax"></a>Синтаксис  
  
```
namespace std {
template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_stringbuf;
typedef basic_stringbuf<char>  
stringbuf;
typedef basic_stringbuf<wchar_t> wstringbuf;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_istringstream;
typedef basic_istringstream<char>  
istringstream;
typedef basic_istringstream<wchar_t> wistringstream;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_ostringstream;
typedef basic_ostringstream<char>  
ostringstream;
typedef basic_ostringstream<wchar_t> wostringstream;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_stringstream;
typedef basic_stringstream<char>  
stringstream;
typedef basic_stringstream<wchar_t> wstringstream;
// TEMPLATE FUNCTIONS
template <class CharType, class Traits, class Allocator>
void swap(
    basic_stringbuf<CharType, Traits, Allocator>& left,
    basic_stringbuf<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap(
    basic_istringstream<CharType, Traits, Allocator>& left,
    basic_istringstream<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap(
    basic_ostringstream<CharType, Traits, Allocator>& left,
    basic_ostringstream<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap (
    basic_stringstream<CharType, Traits, Allocator>& left,
    basic_stringstream<CharType, Traits, Allocator>& right);

}  // namespace std
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`left`|Ссылка на объект `sstream`.|  
|`right`|Ссылка на объект `sstream`.|  
  
## <a name="remarks"></a>Примечания  
 Объекты типа `char *` могут использовать функциональность объекта [\<strstream>](../standard-library/strstream.md) для потоковой передачи. Однако вместо `<strstream>` рекомендуется использовать `<sstream>`.  
  
### <a name="typedefs"></a>Определения типов  
  
|||  
|-|-|  
|[istringstream](../standard-library/sstream-typedefs.md#istringstream)|Создает тип `basic_istringstream`, специализированный на параметре шаблона `char`.|  
|[ostringstream](../standard-library/sstream-typedefs.md#ostringstream)|Создает тип `basic_ostringstream`, специализированный на параметре шаблона `char`.|  
|[stringbuf](../standard-library/sstream-typedefs.md#stringbuf)|Создает тип `basic_stringbuf`, специализированный на параметре шаблона `char`.|  
|[stringstream](../standard-library/sstream-typedefs.md#stringstream)|Создает тип `basic_stringstream`, специализированный на параметре шаблона `char`.|  
|[wistringstream](../standard-library/sstream-typedefs.md#wistringstream)|Создает тип `basic_istringstream`, специализированный на параметре шаблона `wchar_t`.|  
|[wostringstream](../standard-library/sstream-typedefs.md#wostringstream)|Создает тип `basic_ostringstream`, специализированный на параметре шаблона `wchar_t`.|  
|[wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf)|Создает тип `basic_stringbuf`, специализированный на параметре шаблона `wchar_t`.|  
|[wstringstream](../standard-library/sstream-typedefs.md#wstringstream)|Создает тип `basic_stringstream`, специализированный на параметре шаблона `wchar_t`.|  
  
### <a name="manipulators"></a>Манипуляторы  
  
|||  
|-|-|  
|[swap](../standard-library/sstream-functions.md#sstream_swap)|Меняет местами значения двух объектов `sstream`.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[basic_stringbuf](../standard-library/basic-stringbuf-class.md)|Описывает буфер потока, который управляет передачей элементов типа **Elem**, признаки символов которого определяются с помощью класса **Tr**, в последовательность элементов, сохраненную в объекте массива, и из нее.|  
|[basic_istringstream](../standard-library/basic-istringstream-class.md)|Описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`> с элементами типа **Elem**, признаки символов которых определяются классом **Tr**, а элементы выделяются распределителем класса `Alloc`.|  
|[basic_ostringstream](../standard-library/basic-ostringstream-class.md)|Описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`> с элементами типа **Elem**, признаки символов которых определяются классом **Tr**, а элементы выделяются распределителем класса `Alloc`.|  
|[basic_stringstream](../standard-library/basic-stringstream-class.md)|Описывает объект, управляющий извлечением и вставкой элементов и закодированных объектов с помощью буфера потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`> с элементами типа **Elem**. Их признаки символов определяются классом **Tr**, а элементы выделяются распределителем класса `Alloc`.|  
  
## <a name="requirements"></a>Требования  
  
- **Заголовок:** \<sstream>  
  
- **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../standard-library/iostream-programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)



