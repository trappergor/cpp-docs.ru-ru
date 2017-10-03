---
title: "Класс wstring_convert | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- wstring/stdext::cvt::wstring_convert
- locale/std::wstring_convert::byte_string
- locale/std::wstring_convert::wide_string
- locale/std::wstring_convert::state_type
- locale/std::wstring_convert::int_type
- locale/std::wstring_convert::from_bytes
- locale/std::wstring_convert::to_bytes
- locale/std::wstring_convert::converted
- locale/std::wstring_convert::state
dev_langs:
- C++
helpviewer_keywords:
- stdext::cvt [C++], wstring_convert
- std::wstring_convert [C++], byte_string
- std::wstring_convert [C++], wide_string
- std::wstring_convert [C++], state_type
- std::wstring_convert [C++], int_type
- std::wstring_convert [C++], from_bytes
- std::wstring_convert [C++], to_bytes
- std::wstring_convert [C++], converted
- std::wstring_convert [C++], state
ms.assetid: e34f5b65-d572-4bdc-ac69-20778712e376
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 926edb3f3e1a362509b0f57ef2ae930faa7321ac
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="wstringconvert-class"></a>Класс wstring_convert
Класс шаблона `wstring_convert` выполняет преобразование между строкой двухбайтовых символов и строкой байтовых символов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Codecvt, class Elem = wchar_t>
class wstring_convert
```  
  
#### <a name="parameters"></a>Параметры  
 Codecvt  
 Аспект [языкового стандарта](../standard-library/locale-class.md), представляющий объект преобразования.  
  
 Elem  
 Тип двухбайтового элемента.  
  
## <a name="remarks"></a>Примечания  
 Класс шаблона описывает объект, управляющий преобразованием между объектами двухбайтовых строк класса `std::basic_string<Elem>` и объектов однобайтовых строк класса `std::basic_string<char>` (они также называются `std::string`). Класс шаблона определяет типы `wide_string` и `byte_string` как синонимы для этих двух типов. Преобразование между последовательностями значений `Elem` (хранятся в объекте `wide_string`) и многобайтовыми последовательностями (хранятся в объекте `byte_string`) выполняется объектом класса `Codecvt<Elem, char, std::mbstate_t>`, который соответствует требованиям аспекта стандартного преобразования кода `std::codecvt<Elem, char, std::mbstate_t>`.  
  
 Объект этого класса шаблона сохраняет:  
  
-   Однобайтовую строку для отображения при ошибках  
  
-   Двухбайтовую строку для отображения при ошибках  
  
-   Указатель на назначенный объект преобразования (высвобождается при уничтожении объекта wbuffer_convert)  
  
-   Объект состояния для преобразования типа [state_type](#state_type)  
  
-   Счетчик преобразований  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[wstring_convert](#wstring_convert)|Создает объект типа `wstring_convert`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[byte_string](#byte_string)|Тип, представляющий однобайтную строку.|  
|[wide_string](#wide_string)|Тип, представляющий двухбайтную строку.|  
|[state_type](#state_type)|Тип, представляющий состояние преобразования.|  
|[int_type](#int_type)|Тип, представляющий целое число.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[from_bytes](#from_bytes)|Преобразует строку однобайтовых символов в строку двухбайтовых символов.|  
|[to_bytes](#to_bytes)|Преобразует двухбайтовую строку в однобайтовую.|  
|[converted](#converted)|Возвращает количество успешных преобразований.|  
|[state](#state)|Возвращает объект, представляющий состояние преобразования.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<locale>  
  
 **Пространство имен:** std  
  
##  <a name="byte_string"></a>  wstring_convert::byte_string  
 Тип, представляющий однобайтную строку.  
  
```
typedef std::basic_string<char> byte_string;
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом `std::basic_string<char>`.  
  
##  <a name="converted"></a>  wstring_convert::converted  
 Возвращает количество успешных преобразований.  
  
```
size_t converted() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число успешных преобразований.  
  
### <a name="remarks"></a>Примечания  
 Число успешных преобразований хранится в объекте счетчика преобразований.  
  
##  <a name="from_bytes"></a>  wstring_convert::from_bytes  
 Преобразует строку однобайтовых символов в строку двухбайтовых символов.  
  
```
wide_string from_bytes(char Byte);
wide_string from_bytes(const char* ptr);
wide_string from_bytes(const byte_string& Bstr);
wide_string from_bytes(const char* first, const char* last);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`Byte`|Последовательность одноэлементных байт для преобразования.|  
|`ptr`|Последовательность символов в стиле С, оканчивающаяся нулем, для преобразования.|  
|`Bstr`|Строка [byte_string](#byte_string) для преобразования.|  
|`first`|Первый символ в диапазоне символов для преобразования.|  
|`last`|Последний символ в диапазоне символов для преобразования.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект строки двухбайтовых символов, полученный в результате преобразования.  
  
### <a name="remarks"></a>Примечания  
 Если объект [состояния преобразования](../standard-library/wstring-convert-class.md) был создан `not` с явным значением, то перед началом преобразования ему присваивается значение по умолчанию (начальное состояние преобразования). В противном случае он остается неизменным.  
  
 Количество успешно преобразованных входных элементов сохраняется в объекте счетчика преобразования. При отсутствии ошибок преобразования функция-член возвращает преобразованную двухбайтовую строку. В противном случае, если объект был создан с помощью инициализатора сообщения об ошибке в двухбайтовой строке, функция-член возвращает объект сообщения об ошибке в двухбайтовой строке. В противном случае функция-член создает объект класса [range_error](../standard-library/range-error-class.md).  
  
##  <a name="int_type"></a>  wstring_convert::int_type  
 Тип, представляющий целое число.  
  
```
typedef typename wide_string::traits_type::int_type int_type;
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом `wide_string::traits_type::int_type`.  
  
##  <a name="state"></a>  wstring_convert::state  
 Возвращает объект, представляющий состояние преобразования.  
  
```
state_type state() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [состояния преобразования](../standard-library/wstring-convert-class.md), который представляет состояние преобразования.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="state_type"></a>  wstring_convert::state_type  
 Тип, представляющий состояние преобразования.  
  
```
typedef typename Codecvt::state_type state_type;
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает объект, который может представлять состояние преобразования. Тип является синонимом `Codecvt::state_type`.  
  
##  <a name="to_bytes"></a>  wstring_convert::to_bytes  
 Преобразует двухбайтовую строку в однобайтовую.  
  
```
byte_string to_bytes(Elem Char);
byte_string to_bytes(const Elem* Wptr);
byte_string to_bytes(const wide_string& Wstr);
byte_string to_bytes(const Elem* first, const Elem* last);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`Char`|Расширенный символ для преобразования.|  
|`Wptr`|Последовательность в стиле C, оканчивающаяся нулем, начинающаяся с `wptr`, для преобразования.|  
|`Wstr`|Строка [wide_string](#wide_string) для преобразования.|  
|`first`|Первый элемент в диапазоне преобразуемых элементов.|  
|`last`|Последний элемент в диапазоне преобразуемых элементов.|  
  
### <a name="remarks"></a>Примечания  
 Если объект [состояния преобразования](../standard-library/wstring-convert-class.md) был создан `not` с явным значением, то перед началом преобразования ему присваивается значение по умолчанию (начальное состояние преобразования). В противном случае он остается неизменным.  
  
 Число успешно преобразованных входных элементов сохраняется в объекте счетчика преобразований. При отсутствии ошибок преобразования, функция-член возвращает преобразованную однобайтовую строку. В противном случае, если объект был создан с помощью инициализатора сообщения об ошибке в однобайтовой строке, функция-член возвращает объект сообщения об ошибке в однобайтовой строке. В противном случае функция-член создает объект класса [range_error](../standard-library/range-error-class.md).  
  
##  <a name="wide_string"></a>  wstring_convert::wide_string  
 Тип, представляющий двухбайтную строку.  
  
```
typedef std::basic_string<Elem> wide_string;
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом `std::basic_string<Elem>`.  
  
##  <a name="wstring_convert"></a>  wstring_convert::wstring_convert  
 Создает объект типа `wstring_convert`.  
  
```
wstring_convert(Codecvt *Pcvt = new Codecvt);
wstring_convert(Codecvt *Pcvt, state_type _State);
wstring_convert(const byte_string& _Berr, const wide_string& Werr = wide_string());
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`*Pcvt`|Объект типа `Codecvt` для выполнения преобразования.|  
|`_State`|Объект типа [state_type](#state_type), представляющий состояние преобразования.|  
|`_Berr`|Объект [byte_string](#byte_string) для отображения ошибок.|  
|`Werr`|Объект [wide_string](#wide_string) для отображения ошибок.|  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор сохраняет *Pcvt_arg* в [объекте преобразования](../standard-library/wstring-convert-class.md)

