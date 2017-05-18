---
title: "Операторы &lt;functional&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- functional/std::operator!=
- functional/std::operator==
dev_langs:
- C++
helpviewer_keywords:
- functional operators
ms.assetid: d4b3c760-f3e2-4b65-bdaa-d42e8dd6f5e1
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: f38d129aab8703b6077b2848d7b71bb0a07e0ea7
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="ltfunctionalgt-operators"></a>Операторы &lt;functional&gt;
|||  
|-|-|  
|[оператор!=](#op_neq)|[оператор==](#op_eq_eq)|  
  
##  <a name="op_eq_eq"></a>  оператор==  
 Проверяет, является ли вызываемый объект пустым.  
  
```  
template <class Fty>  
bool operator==(const function<Fty>& f, null_ptr_type npc);

template <class Fty>  
bool operator==(null_ptr_type npc, const function<Fty>& f);
```  
  
### <a name="parameters"></a>Параметры  
 `Fty`  
 Тип функции для заключения в оболочку.  
  
 `f`  
 Объект функции  
  
 `npc`  
 Указатель null  
  
### <a name="remarks"></a>Примечания  
 Операторы принимают аргумент, являющийся ссылкой на объект `function`, и аргумент, являющийся константой указателя null. В обоих случаях возвращается значение true только в том случае, если объект `function` пуст.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__functional__operator_eq.cpp
// compile with: /EHsc   
#include <functional>   
#include <iostream>   

int neg(int val)
{
    return (-val);
}

int main()
{
    std::function<int(int)> fn0;
    std::cout << std::boolalpha << "empty == "
        << (fn0 == 0) << std::endl;

    std::function<int(int)> fn1(neg);
    std::cout << std::boolalpha << "empty == "
        << (fn1 == 0) << std::endl;

    return (0);
}
  
```  
  
```Output  
empty == true  
empty == false  
```  
  
##  <a name="op_neq"></a>  оператор!=  
 Проверяет, является ли вызываемый объект не пустым.  
  
```  
template <class Fty>  
bool operator!=(const function<Fty>& f, null_ptr_type npc);

template <class Fty>  
bool operator!=(null_ptr_type npc, const function<Fty>& f);
```  
  
### <a name="parameters"></a>Параметры  
 `Fty`  
 Тип функции для заключения в оболочку.  
  
 `f`  
 Объект функции  
  
 `npc`  
 Указатель null  
  
### <a name="remarks"></a>Примечания  
 Операторы принимают аргумент, являющийся ссылкой на объект `function`, и аргумент, являющийся константой указателя null. В обоих случаях возвращается значение true только в том случае, если объект `function` не пуст.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__functional__operator_ne.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val)   
    {   
    return (-val);   
    }   
  
int main()   
    {   
    std::function<int (int)> fn0;   
    std::cout << std::boolalpha << "not empty == "   
        << (fn0 != 0) << std::endl;   
  
    std::function<int (int)> fn1(neg);   
    std::cout << std::boolalpha << "not empty == "   
        << (fn1 != 0) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
not empty == false  
not empty == true  
```  
  
## <a name="see-also"></a>См. также  
 [\<functional>](../standard-library/functional.md)


