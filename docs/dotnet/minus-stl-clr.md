---
title: "минус (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::minus
dev_langs: C++
helpviewer_keywords: minus function [STL/CLR]
ms.assetid: 810ec6fd-ed0e-446b-b18e-1e612fb1fff4
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 76017cd4a63f6c8bd1956c6f871fc10027b9b6d1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="minus-stlclr"></a>minus (STL/CLR)
Класс шаблона описывает функтор, при вызове возвращает первый аргумент минус за секунду. Она используется укажите объект функции, с точки зрения его типа аргумента.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Arg>  
    ref class minus  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef Arg result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    minus();  
    minus(minus<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>Параметры  
 Arg  
 Тип аргументов и возвращаемого значения.  
  
## <a name="member-functions"></a>Функции-члены  
  
|Определение типа|Описание|  
|---------------------|-----------------|  
|delegate_type|Тип универсального метода-делегата.|  
|first_argument_type|Тип первого аргумента функтор.|  
|result_type|Тип результата функтор.|  
|second_argument_type|Тип второго аргумента функтор.|  
  
|Член|Описание|  
|------------|-----------------|  
|minus|Создает функтор.|  
  
|Оператор|Описание|  
|--------------|-----------------|  
|operator()|Вычисляет нужной функции.|  
|delegate_type оператор ^|Приводит функтора к делегату.|  
  
## <a name="remarks"></a>Примечания  
 Класс шаблона описывает функтор двумя аргументами. Он определяет оператор-член `operator()` , чтобы при вызове объекта как функцию, он возвращает первый аргумент минус за секунду.  
  
 Объект также можно передать в качестве аргумента функции, тип которого является `delegate_type^` и он будет преобразован соответствующим образом.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_minus.cpp   
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
    c2.push_back(2);   
    c2.push_back(1);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 2 1"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::minus<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
2 1  
2 2  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext и функционального >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [plus (STL/CLR)](../dotnet/plus-stl-clr.md)