---
title: "binder2nd (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::binder2nd
dev_langs: C++
helpviewer_keywords: binder2nd function [STL/CLR]
ms.assetid: f4be8722-1778-4cb9-9ec7-ad1443f6899f
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b22c435952602afe96a7f310b931bda8a5bbb13c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="binder2nd-stlclr"></a>binder2nd (STL/CLR)
Класс шаблона описывает функтор один аргумент, при вызове возвращает его хранимых функтор два аргумента, вызывается с помощью предоставленного аргумента первого и второго аргумента хранимой. Она используется укажите объект функции, с точки зрения его хранимых функтор.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Fun>  
    ref class binder2nd  
    { // wrap operator()  
public:  
    typedef Fun stored_function_type;  
    typedef typename Fun::first_argument_type first_argument_type;  
    typedef typename Fun::second_argument_type second_argument_type;  
    typedef typename Fun:result_type result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        first_argument_type, result_type>  
        delegate_type;  
  
    binder2nd(Fun% functor, second_argument_type left);  
    binder2nd(binder2nd<Arg>% right);  
  
    result_type operator()(first_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>Параметры  
 Fun  
 Тип хранимой функтора.  
  
## <a name="member-functions"></a>Функции-члены  
  
|Определение типа|Описание:|  
|---------------------|-----------------|  
|delegate_type|Тип универсального метода-делегата.|  
|first_argument_type|Тип первого аргумента функтор.|  
|result_type|Тип результата функтор.|  
|second_argument_type|Тип второго аргумента функтор.|  
|stored_function_type|Тип функтора.|  
  
|Член|Описание:|  
|------------|-----------------|  
|binder2nd|Создает функтор.|  
  
|Оператор|Описание:|  
|--------------|-----------------|  
|operator()|Вычисляет нужной функции.|  
|оператор delegate_type^()|Приводит функтора к делегату.|  
  
## <a name="remarks"></a>Примечания  
 Класс шаблона описывает функтор один аргумент, который хранит функтор два аргумента и второй аргумент. Он определяет оператор-член `operator()` , чтобы при вызове объекта как функцию, он возвращает результат вызова хранимых функтор с предоставленного аргумента первого и второго аргумента хранимой.  
  
 Объект также можно передать в качестве аргумента функции, тип которого является `delegate_type^` и он будет преобразован соответствующим образом.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_binder2nd.cpp   
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
    Myvector c3(2, 0);   
  
// display initial contents " 4 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::minus<int> sub_op;   
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        sub4);   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        bind2nd(sub_op, 4));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
0 -1  
0 -1  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext и функционального >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [bind2nd (STL/CLR)](../dotnet/bind2nd-stl-clr.md)