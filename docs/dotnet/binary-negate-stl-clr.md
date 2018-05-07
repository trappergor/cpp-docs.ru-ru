---
title: binary_negate (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::binary_negate
dev_langs:
- C++
helpviewer_keywords:
- binary_negate function [STL/CLR]
ms.assetid: 0c3b47eb-0f37-4cb2-b879-4c9f0e57d275
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f78f7ab24fdaf48205fc899031c396a2d8e3947e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="binarynegate-stlclr"></a>binary_negate (STL/CLR)
Класс шаблона описывает функтор, при вызове возвращает логический, ОТЛИЧНОГО от его хранимых функтор двумя аргументами. Она используется укажите объект функции, с точки зрения его хранимых функтор.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Fun>  
    ref class binary_negate  
    { // wrap operator()  
public:  
    typedef Fun stored_function_type;  
    typedef typename Fun::first_argument_type first_argument_type;  
    typedef typename Fun::second_argument_type second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    explicit binary_negate(Fun% functor);  
    binary_negate(binary_negate<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>Параметры  
 Fun  
 Тип хранимой функтора.  
  
## <a name="member-functions"></a>Функции-члены  
  
|Определение типа|Описание|  
|---------------------|-----------------|  
|delegate_type|Тип универсального метода-делегата.|  
|first_argument_type|Тип первого аргумента функтор.|  
|result_type|Тип результата функтор.|  
|second_argument_type|Тип второго аргумента функтор.|  
|stored_function_type|Тип функтора.|  
  
|Член|Описание|  
|------------|-----------------|  
|binary_negate|Создает функтор.|  
  
|Оператор|Описание|  
|--------------|-----------------|  
|operator()|Вычисляет нужной функции.|  
|оператор delegate_type^()|Приводит функтора к делегату.|  
  
## <a name="remarks"></a>Примечания  
 Класс шаблона описывает функтор два аргумента, который хранит другой функтор двумя аргументами. Он определяет оператор-член `operator()` , чтобы при вызове объекта как функцию, он возвращает логический, ОТЛИЧНОГО от хранимых функтор вызывается с двумя аргументами.  
  
 Объект также можно передать в качестве аргумента функции, тип которого является `delegate_type^` и он будет преобразован соответствующим образом.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_binary_negate.cpp   
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
    cliext::less<int> less_op;   
  
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(),   
        cliext::binary_negate<cliext::less<int> >(less_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::not2(less_op));   
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
1 0  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext и функционального >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [not2 (STL/CLR)](../dotnet/not2-stl-clr.md)