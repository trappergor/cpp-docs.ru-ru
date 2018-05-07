---
title: Ошибка компилятора C3530 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3530
dev_langs:
- C++
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6514d655ab813ae21ecb440415f87bce63f3591
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3530"></a>Ошибка компилятора C3530
«auto» не может объединяться с любыми другими спецификаторами типа  
  
 Описатель типа используется с `auto` ключевое слово.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Не используйте описатель типа в объявлении переменной, которая использует `auto` ключевое слово.  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3530, так как переменная `x` объявлен с обоими `auto` ключевое слово и тип `int`, а потому, что код примера компилируется с **/Zc: auto**.  
  
```  
// C3530.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto int x;   // C3530  
   return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевое слово auto](../../cpp/auto-keyword.md)