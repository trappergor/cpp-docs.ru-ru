---
title: C2178 Ошибка компилятора | Документы Microsoft
ms.custom: ''
ms.date: 05/08/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2178
dev_langs:
- C++
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3727a66554b2e128061820df160c02a1370ebb74
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2178"></a>C2178 ошибки компилятора  
  
"*идентификатор*«не может объявляться с»*описатель*" спецификатор  
  
Объект `mutable` используется спецификатор в объявлении, но спецификатора не допускается в данном контексте.  
  
`mutable` Указателя может применяться только к именам членов класса данных и не может применяться к именам, объявленным `const` или `static`и не может применяться к элементам ссылки.  
  
## <a name="example"></a>Пример  
  
Следующий пример показывает, как может возникнуть C2178 и способы ее устранения.  
  
```  
// C2178.cpp
// compile with: cl /c /W4 C2178.cpp

class S {
    mutable const int i; // C2178
    // To fix, declare either const or mutable, not both.
};

mutable int x = 4; // C2178
// To fix, remove mutable keyword
```  
