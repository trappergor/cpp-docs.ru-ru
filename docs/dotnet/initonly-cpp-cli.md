---
title: initonly (C + +/ CLI) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
f1_keywords:
- initonly_cpp
- initonly
dev_langs:
- C++
helpviewer_keywords:
- initonly attribute [C++]
ms.assetid: f745d7fa-dc08-46f1-9b97-0977be58a008
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 49c52c4c17c3e54bfba0ac7188b3300b132213cc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130559"
---
# <a name="initonly-ccli"></a>initonly (C++/CLI)
**initonly** заключается в контекстно-зависимое ключевое слово, которое указывает, что присваивания значения переменной может выполняться только в рамках объявления или в статическом конструкторе в том же классе.  
  
 В следующем примере показано использование `initionly`.  
  
```  
// mcpp_initonly.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   initonly  
   static int staticConst1;  
  
   initonly  
   static int staticConst2 = 0;  
  
   static Y1() {  
      staticConst1 = 0;  
   }  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)