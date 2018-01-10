---
title: "Класс add_rvalue_reference | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::add_rvalue_reference
dev_langs: C++
helpviewer_keywords: add_rvalue_reference Class
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 605e428c0712a657b7b3d0df35558a61c6dbc54a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="addrvaluereference-class"></a>Класс add_rvalue_reference
Создает ссылочный тип rvalue параметра-шаблона, если он является типом объекта или функции. В противном случае из-за семантики сворачивания ссылок этот тип является таким же, как параметр шаблона.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template <class T>
struct add_rvalue_reference;

template <class T>
using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;
```  
  
#### <a name="parameters"></a>Параметры  
 T  
 Тип для изменения.  
  
## <a name="remarks"></a>Примечания  
 Класс `add_rvalue_reference` содержит член с именем `type`, который является псевдонимом для типа ссылки rvalue на параметр шаблона `T`. Семантика сворачивания ссылок подразумевает, что для типов `T`, не являющихся типами объектов или функций, `T&&` — `T`. Например, если `T` является типом ссылки lvalue `add_rvalue_reference<T>::type` является ссылочным типом lvalue, а не ссылкой rvalue.  
  
 Для удобства <type_traits> определяет вспомогательный шаблон `add_rvalue_reference_t`, который задает псевдоним члена `type` `add_rvalue_reference`.  
  
## <a name="example"></a>Пример  
 В данном примере кода используется static_assert, чтобы показать, как ссылочные типы rvalue создаются с помощью `add_rvalue_reference` и `add_rvalue_reference_t`, и что результат `add_rvalue_reference` в ссылочном типе lvalue не является ссылкой rvalue, но сворачивается до ссылочного типа lvalue.  
  
```cpp  
// ex_add_rvalue_reference.cpp  
// Build by using: cl /EHsc /W4 ex_add_rvalue_reference.cpp  
#include <type_traits>   
#include <iostream>   
#include <string>  
  
using namespace std;  
int main()  
{  
    static_assert(is_same<add_rvalue_reference<string>::type, string&&>::value,   
        "Expected add_rvalue_reference_t<string> to be string&&");  
    static_assert(is_same<add_rvalue_reference_t<string*>, string*&&>::value,   
        "Expected add_rvalue_reference_t<string*> to be string*&&");  
    static_assert(is_same<add_rvalue_reference<string&>::type, string&>::value,   
        "Expected add_rvalue_reference_t<string&> to be string&");  
    static_assert(is_same<add_rvalue_reference_t<string&&>, string&&>::value,   
        "Expected add_rvalue_reference_t<string&&> to be string&&");  
    cout << "All static_assert tests of add_rvalue_reference passed." << endl;  
    return 0;  
}  
  
/*Output:  
All static_assert tests of add_rvalue_reference passed.  
*/  
```  
  
## <a name="requirements"></a>Требования  
 Заголовок: <type_traits> Пространство имен: std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)   
 [Класс add_lvalue_reference](../standard-library/add-lvalue-reference-class.md)   
 [Класс is_rvalue_reference](../standard-library/is-rvalue-reference-class.md)
