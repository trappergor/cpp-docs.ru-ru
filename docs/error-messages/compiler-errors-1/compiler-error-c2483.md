---
title: "Ошибка компилятора C2483 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2483
dev_langs:
- C++
helpviewer_keywords:
- C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
caps.latest.revision: 10
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 391be3c032bc48a20304befec1fb61cbe14e7f60
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2483"></a>Ошибка компилятора C2483
«Идентификатор»: объект с конструктором или деструктором не может объявляться как «thread»  
  
 Переменные, объявленные с `thread` атрибута не может инициализироваться с конструктором или другим выражением, которое требуется вычисление во время выполнения. Статическое выражение необходим для инициализации `thread` данных.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2483.  
  
```  
// C2483.cpp  
// compile with: /c  
__declspec(thread) struct A {  
   A(){}  
   ~A(){}  
} aa;   // C2483 error  
  
__declspec(thread) struct B {} b;   // OK  
```  
  
## <a name="see-also"></a>См. также  
 [поток](../../cpp/thread.md)
