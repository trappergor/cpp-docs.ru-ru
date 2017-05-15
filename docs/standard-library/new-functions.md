---
title: "Функции &lt;new&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- new/std::nothrow
- new/std::set_new_handler
ms.assetid: e250f06a-b025-4509-ae7a-5356d56aad7d
caps.latest.revision: 10
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 53a31f533ee777dbbcc486283034094481ab0c31
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="ltnewgt-functions"></a>Функции &lt;new&gt;
|||  
|-|-|  
|[nothrow](#nothrow)|[set_new_handler](#set_new_handler)|  
  
##  <a name="nothrow"></a>  nothrow  
 Предоставляет объект для использования в качестве аргумента для версий `nothrow` **new** и **delete**.  
  
```  
extern const std::nothrow_t nothrow;  
```  
  
### <a name="remarks"></a>Примечания  
 Объект используется в качестве аргумента функции для соответствия типу параметра [std::nothrow_t](../standard-library/nothrow-t-structure.md).  
  
### <a name="example"></a>Пример  
  См. разделы [operator new](../standard-library/new-operators.md#op_new) и [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr) с примерами использования `std::nothrow_t` в качестве параметра функции.  
  
##  <a name="set_new_handler"></a>  set_new_handler  
 Устанавливает пользовательскую функцию, вызываемую в случае сбоя `operator new` при попытке выделения памяти.  
  
```  
new_handler set_new_handler(new_handler Pnew) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `Pnew`  
 New_handler для установки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 0 для первого вызова и предыдущее `new_handler` при последующих вызовах.  
  
### <a name="remarks"></a>Примечания  
 Функция сохраняет `Pnew` в статическом указателе [нового обработчика](../standard-library/new-typedefs.md#new_handler), с которым она работает, затем возвращает значение, ранее хранившееся в указателе. Новый обработчик используется [оператором new](../standard-library/new-operators.md#op_new)( **size_t**).  
  
### <a name="example"></a>Пример  
  
```cpp  
// new_set_new_handler.cpp  
// compile with: /EHsc  
#include<new>  
#include<iostream>  
  
using namespace std;  
void __cdecl newhandler( )  
{  
   cout << "The new_handler is called:" << endl;  
   throw bad_alloc( );  
   return;  
}  
  
int main( )   
{  
   set_new_handler (newhandler);  
   try  
   {  
      while ( 1 )   
      {  
         new int[5000000];  
         cout << "Allocating 5000000 ints." << endl;  
      }  
   }  
   catch ( exception e )  
   {  
      cout << e.what( ) << endl;  
   }  
}  
```  
  
```Output  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
The new_handler is called:  
bad allocation  
```  
  
## <a name="see-also"></a>См. также  
 [\<new>](../standard-library/new.md)


