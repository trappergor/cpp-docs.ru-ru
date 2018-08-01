---
title: alignof и alignas (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c10821f7e71c928fa749c2b85bd076cb9af6d04a
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402420"
---
# <a name="alignof-and-alignas-c"></a>alignof и alignas (C++)
**Alignas** спецификатор типа — это стандартный способ переносимый C++ для задания настраиваемого выравнивания переменных и определяемых пользователем типов. **Alignof** оператор — аналогичен стандартному переносимому способу получения выравнивания указанного типа или переменной.  
  
## <a name="example"></a>Пример  
 Можно использовать **alignas** для класса, прохода или объединения, или для отдельных членов. Когда несколько **alignas** спецификаторы встречаются, компилятор выберет наиболее строгом тот (один с наибольшим значением).  
  
```cpp  
// alignas_alignof.cpp
// compile with: cl /EHsc alignas_alignof.cpp
#include <iostream>

struct alignas(16) Bar  
{      
    int i;       // 4 bytes  
    int n;      // 4 bytes  
    alignas(4) char arr[3];  
    short s;          // 2 bytes  
};  

int main()
{  
    std::cout << alignof(Bar) << std::endl; // output: 16  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Выравнивание](../cpp/alignment-cpp-declarations.md)