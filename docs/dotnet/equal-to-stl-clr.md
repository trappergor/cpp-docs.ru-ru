---
title: "equal_to (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::equal_to
dev_langs:
- C++
helpviewer_keywords:
- equal_to function [STL/CLR]
ms.assetid: 9dd6e27d-e695-470f-b7a7-19a6db970ee5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 824fe03c771e0da40f9a587ad076df03604fd53c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="equalto-stlclr"></a>equal_to (STL/CLR)
Класс шаблона описывает функтор, что при вызове возвращает значение true только в том случае, если первый аргумент равен второму. Она используется укажите объект функции, с точки зрения его типа аргумента.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Arg>  
    ref class equal_to  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    equal_to();  
    equal_to(equal_to<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>Параметры  
 Arg  
 Тип аргументов.  
  
## <a name="member-functions"></a>Функции-члены  
  
|Определение типа|Описание:|  
|---------------------|-----------------|  
|delegate_type|Тип универсального метода-делегата.|  
|first_argument_type|Тип первого аргумента функтор.|  
|result_type|Тип результата функтор.|  
|second_argument_type|Тип второго аргумента функтор.|  
  
|Член|Описание:|  
|------------|-----------------|  
|equal_to|Создает функтор.|  
  
|Оператор|Описание:|  
|--------------|-----------------|  
|operator()|Вычисляет нужной функции.|  
|оператор delegate_type^()|Приводит функтора к делегату.|  
  
## <a name="remarks"></a>Примечания  
 Класс шаблона описывает функтор двумя аргументами. Он определяет оператор-член `operator()` , чтобы при вызове объекта как функция, возвращается значение true, только если первый аргумент равен второму.  
  
 Объект также можно передать в качестве аргумента функции, тип которого является `delegate_type^` и он будет преобразован соответствующим образом.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_equal_to.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(4);   
    c2.push_back(4);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 4 4"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::equal_to<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
4 4  
1 0  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext и функционального >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [not_equal_to (STL/CLR)](../dotnet/not-equal-to-stl-clr.md)