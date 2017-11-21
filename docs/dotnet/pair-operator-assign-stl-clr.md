---
title: "Pair::operator = (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::pair::operator=
dev_langs: C++
helpviewer_keywords: operator= member [STL/CLR]
ms.assetid: b6228037-914e-4efa-8491-65dbb0e93f61
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: aa722f53c9ad76c32486d493db6d37e70ce12879
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="pairoperator-stlclr"></a>pair::operator= (STL/CLR)
Заменяет хранимых пара значений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 right  
 Пара для копирования.  
  
## <a name="remarks"></a>Примечания  
 Копирует оператор член `right` объекту, затем возвращает `*this`. Используется для замены хранимой пара значений копию хранимой пары значений в `right`.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_pair_operator_as.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
// assign to a new pair   
    cliext::pair<wchar_t, int> c2;   
    c2 = c1;   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 3]  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/программа >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [pair (STL/CLR)](../dotnet/pair-stl-clr.md)