---
title: "Предупреждение (уровень 3) C4823 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4823
dev_langs:
- C++
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
caps.latest.revision: 12
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ea03723f9ccae2348a47ae4894097f5cd9f8b5a1
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4823"></a>Предупреждение компилятора (уровень 3) C4823
«функция»: закрепляющих указателей, но очистки использует семантику не включены. Рассмотрите возможность использования/EHa  
  
Отменить закрепление объекта в управляемой куче, на который указывает закрепляющий указатель, определенный в области видимости блока, компилятор имитирует поведение деструкторов локальных классов «изображающий командлет «что деструктор, который имеет закрепляющий указатель. Чтобы обеспечить вызов деструктора после возникновения исключения, необходимо включить очистку объектов, что можно сделать с помощью [/EHsc](../../build/reference/eh-exception-handling-model.md).  
  
Можно также вручную отменить закрепление объекта и игнорировать предупреждение.  
  
## <a name="example"></a>Пример  
Следующий пример приводит к возникновению ошибки C4823.  
  
```  
// C4823.cpp  
// compile with: /clr /W3 /EHa-  
using namespace System;  
  
ref struct G {  
   int m;  
};  
  
void f(G ^ pG) {  
   try {  
      pin_ptr<int> p = &pG->m;  
      // manually unpin, ignore warning  
      // p = nullptr;  
      throw gcnew Exception;  
   }  
   catch(Exception ^) {}  
}   // C4823 warning  
  
int main() {  
   f( gcnew G );  
}  
```  

