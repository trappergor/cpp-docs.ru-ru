---
title: "Операторы &lt;ostream&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 9282a62e-a3d1-4371-a284-fbc9515bb9a2
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 72389624e776a2e8334490c37a5ca628e033ffaa
ms.lasthandoff: 02/24/2017

---
# <a name="ltostreamgt-operators"></a>Операторы &lt;ostream&gt;
||  
|-|  
|[оператор&lt;&lt;](#operator_lt__lt_)|  
  
##  <a name="operator_lt__lt_"></a>  оператор&lt;&lt;  
 Записывает в поток различные типы.  
  
```
template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    const Elem* str);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    Elem _Ch);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    const char* str);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _ostr,
    char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);

template <class _Elem, class _Tr, class T>
basic_ostream <_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>&& _Ostr,
    Ty val);
```  
  
### <a name="parameters"></a>Параметры  
 `_Ch`  
 Символ.  
  
 `_Elem`  
 Тип элемента.  
  
 `_Ostr`  
 Объект `basic_ostream`.  
  
 `str`  
 Строка символов.  
  
 `_Tr`  
 Признаки символа.  
  
 `val`  
 Тип.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поток.  
  
### <a name="remarks"></a>Примечания  
 Класс `basic_ostream` также определяет несколько операторов вставки. Дополнительные сведения см. в разделе [basic_ostream::operator&lt;&lt;](../standard-library/basic-ostream-class.md#basic_ostream_operator_lt_lt_).  
  
 Функция-шаблон  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _ostr,
    const Elem *str);
```  
  
 определяет длину последовательности N = `traits_type::` [length](../standard-library/char-traits-struct.md#char_traits__length)(`str`), начиная с `str`, и вставляет последовательность. Если N < `_Ostr.`[width](../standard-library/ios-base-class.md#ios_base__width), то функция также вставляет повторение из `_Ostr.``width` – N символов заполнения. Повторение предшествует последовательности, если (`_Ostr`. [flags](../standard-library/ios-base-class.md#ios_base__flags) & `adjustfield` != [left](../standard-library/ios-functions.md#left). В противном случае повторение следует за последовательностью. Функция возвращает `_Ostr`.  
  
 Функция-шаблон  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```  
  
 вставляет элемент `_Ch`. Если 1 < `_Ostr.width`, то функция также вставляет повторение из `_Ostr.width` – 1 символов заполнения. Повторение предшествует последовательности, если `_Ostr.flags & adjustfield != left`. В противном случае повторение следует за последовательностью. Он возвращает `_Ostr`.  
  
 Функция-шаблон  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const char *str);
```  
  
 ведет себя так же, как  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const Elem *str);
```  
  
 , за исключением того, что каждый элемент `_Ch` последовательности, начиная с `str`, преобразуется в объект типа `Elem` путем вызова `_Ostr.`[put](../standard-library/basic-ostream-class.md#basic_ostream__put)(`_Ostr.`[widen](../standard-library/basic-ios-class.md#basic_ios__widen)(`_Ch`)).  
  
 Функция-шаблон  
  
``cpp template <class _Elem, class _Tr> basic_ostream<Elem, _Tr>& operator<<( basic_ostream<Elem, _Tr>& _Ostr, char _Ch);
```  
  
 behaves the same as  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```  
  
 за исключением того, что `_Ch` преобразуется в объект типа `Elem` путем вызова `_Ostr.put`(`_Ostr.widen`(`_Ch`)).  
  
 Функция-шаблон  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const char *str);
```  
  
 ведет себя так же, как  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const Elem *str);
```  
  
 (Она не обязательно должна расширять элементы перед их вставкой.)  
  
 Функция-шаблон  
  
```cpp  
template <class _Tr>
basic_ostream<char, Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    char _Ch);
```  
  
 ведет себя так же, как  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```  
  
 (Она не обязательно должна расширять `_Ch` перед его вставкой.)  
  
 Функция-шаблон  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char *str);
```  
  
 возвращает `_Ostr` << (`const char *`) `str`.  
  
 Функция-шаблон  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);
```  
  
 возвращает `_Ostr` << (`char`) `_Ch`.  
  
 Функция-шаблон:  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char *str);
```  
  
 возвращает `_Ostr` << (`const char *`) `str`.  
  
 Функция-шаблон:  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);
```  
  
 возвращает `_Ostr` << (`char`) `_Ch`.  
  
 Функция-шаблон:  
  
```cpp  
template <class _Elem, class _Tr, class T>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<char, _Tr>&& _Ostr,
    T val);
```  
  
 возвращает `_Ostr` `<<` `val` (и в процессе преобразует [ссылку RValue](../cpp/rvalue-reference-declarator-amp-amp.md) в `_Ostr` на lvalue).  
  
### <a name="example"></a>Пример  
  См. раздел [flush](../standard-library/ostream-functions.md#flush) с примером использования `operator<<`.  
  
## <a name="see-also"></a>См. также  
 [\<ostream>](../standard-library/ostream.md)




