---
title: оператор&gt; (вектор) (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::operator>
dev_langs:
- C++
helpviewer_keywords:
- operator> member [STL/CLR]
ms.assetid: c9c55c3f-5e82-4504-90e3-708dab7aa660
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4ca40b85e6335759df2e60e9b87593dd9ad11d9b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33133367"
---
# <a name="operatorgt-vector-stlclr"></a>оператор&gt; (вектор) (STL/CLR)
Вектор, больше, чем сравнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value>  
    bool operator>(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 left  
 Левый контейнер для сравнения.  
  
 right  
 Правый контейнер для сравнения.  
  
## <a name="remarks"></a>Примечания  
 Функция оператор возвращает `right` `<` `left`. Можно использовать для тестирования ли `left` упорядочен после `right` при двух векторов, сравниваемые элемент элемент.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_vector_operator_gt.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] > [a b c] is {0}",   
        c1 > c1);   
    System::Console::WriteLine("[a b d] > [a b c] is {0}",   
        c2 > c1);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] > [a b c] is False  
[a b d] > [a b c] is True  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/vector >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [вектор (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [оператор == (вектор) (STL/CLR)](../dotnet/operator-equality-vector-stl-clr.md)   
 [оператор! = (вектор) (STL/CLR)](../dotnet/operator-inequality-vector-stl-clr.md)   
 [оператор\< (вектор) (STL/CLR)](../dotnet/operator-less-than-vector-stl-clr.md)   
 [оператор > = (вектор) (STL/CLR)](../dotnet/operator-greater-or-equal-vector-stl-clr.md)   
 [operator<= (vector) (STL/CLR)](../dotnet/operator-less-or-equal-vector-stl-clr.md)