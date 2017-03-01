---
title: "Ошибка компилятора C3530 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3530
dev_langs:
- C++
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: ddaa07e0c06a871815f42c4f5d6760befdb06b30
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3530"></a>Ошибка компилятора C3530
"auto" не может объединяться с любыми другими спецификаторами типа  
  
 Описатель типа использован с `auto` ключевое слово.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Не используйте описатель типа в объявлении переменной, которая использует `auto` ключевое слово.  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3530, так как переменная `x` объявляется как с `auto` ключевое слово и тип `int`, и поскольку код примера компилируется с **/Zc: auto**.  
  
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
 [Ключевое слово Auto](../../cpp/auto-keyword.md)
