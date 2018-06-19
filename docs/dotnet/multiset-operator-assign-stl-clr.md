---
title: MULTISET::operator = (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multiset::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= member [STL/CLR]
ms.assetid: 74e60042-d0d6-471f-8fdb-79b3c6856440
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1661f47399aa8fc4d1ddeeef546855bb16ac71cc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33131583"
---
# <a name="multisetoperator-stlclr"></a>multiset::operator= (STL/CLR)
Заменяет управляемую последовательность.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
multiset<Key>% operator=(multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 right  
 Контейнер для копирования.  
  
## <a name="remarks"></a>Примечания  
 Копирует оператор член `right` объекту, затем возвращает `*this`. Он позволяет заменить управляемую последовательность копией управляемой последовательности в `right`.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_multiset_operator_as.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (Mymultiset::value_type elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2 = c1;   
// display contents " a b c"   
    for each (Mymultiset::value_type elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext и set >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)