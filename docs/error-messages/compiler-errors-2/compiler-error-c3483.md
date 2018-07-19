---
title: Ошибка компилятора C3483 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3483
dev_langs:
- C++
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e2605674ff701f70f7be6ea1b4158c9f8f0c6ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33258741"
---
# <a name="compiler-error-c3483"></a>Ошибка компилятора C3483
var уже является частью списка передаваемых параметров лямбда-выражения  
  
 Вы несколько раз передали одну и ту же переменную в список передаваемых параметров лямбда-выражения.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите все дополнительные экземпляры переменной из списка передаваемых параметров.  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C3483, так как в списке передаваемых параметров лямбда-выражения переменная `n` присутствует несколько раз.  
  
```  
// C3483.cpp  
  
int main()  
{  
   int m = 6, n = 5;  
   [m,n,n] { return n + m; }(); // C3483  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)