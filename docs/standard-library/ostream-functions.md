---
title: "Функции &lt;ostream&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ostream/std::swap
- ostream/std::endl
- ostream/std::ends
- ostream/std::flush
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
caps.latest.revision: 15
manager: ghogen
helpviewer_keywords:
- std::swap [C++]
- std::endl [C++]
- std::ends [C++]
- std::flush [C++]
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 252a178f1ce71c30bdd830811cbce59b22acc791
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="ltostreamgt-functions"></a>Функции &lt;ostream&gt;
||||  
|-|-|-|  
|[swap](#swap)|[endl](#endl)|[ends](#ends)|  
|[flush](#flush)|  
  
##  <a name="endl"></a>  endl  
 Завершает строку и очищает буфер.  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& endl(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>Параметры  
 `Elem`  
 Тип элемента.  
  
 `Ostr`  
 Объект типа `basic_ostream`.  
  
 `Tr`  
 Признаки символа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект типа `basic_ostream`.  
  
### <a name="remarks"></a>Примечания  
 Манипулятор вызывает `Ostr`**.**[put](../standard-library/basic-ostream-class.md#put)( `Ostr`**.** [widen](../standard-library/basic-ios-class.md#widen)( **'\n'**)), а затем вызывает `Ostr`**.**[flush](../standard-library/basic-ostream-class.md#flush). Он возвращает `Ostr`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// ostream_endl.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "testing" << endl;  
}  
```  
  
```Output  
testing  
```  
  
##  <a name="ends"></a>  ends  
 Завершает строку.  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& ends(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>Параметры  
 `Elem`  
 Тип элемента.  
  
 `Ostr`  
 Объект типа `basic_ostream`.  
  
 `Tr`  
 Признаки символа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект типа `basic_ostream`.  
  
### <a name="remarks"></a>Примечания  
 Манипулятор вызывает `Ostr`**.**[put](../standard-library/basic-ostream-class.md#put)( `Elem`( **'\0'**)). Он возвращает `Ostr.`  
  
### <a name="example"></a>Пример  
  
```cpp  
// ostream_ends.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "a";  
   cout << "b" << ends;  
   cout << "c" << endl;  
}  
```  
  
```Output  
ab c  
```  
  
##  <a name="flush"></a>  flush  
 Очищает буфер.  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& flush(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>Параметры  
 `Elem`  
 Тип элемента.  
  
 `Ostr`  
 Объект типа `basic_ostream`.  
  
 `Tr`  
 Признаки символа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект типа `basic_ostream`.  
  
### <a name="remarks"></a>Примечания  
 Манипулятор вызывает `Ostr`**.**[flush](../standard-library/basic-ostream-class.md#flush). Он возвращает `Ostr`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// ostream_flush.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "testing" << flush;  
}  
```  
  
```Output  
testing  
```  
  
##  <a name="swap"></a>  swap  
 Меняет местами значения двух объектов `basic_ostream`.  
  
```  
template <class Elem, class Tr>  
void swap(
    basic_ostream<Elem, Tr>& left,  
    basic_ostream<Elem, Tr>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Ссылка lvalue на объект `basic_ostream`.  
  
 `right`  
 Ссылка lvalue на объект `basic_ostream`.  
  
### <a name="remarks"></a>Примечания  
 Функция шаблона `swap` выполняет `left.swap(right)`.  
  
## <a name="see-also"></a>См. также  
 [\<ostream>](../standard-library/ostream.md)


