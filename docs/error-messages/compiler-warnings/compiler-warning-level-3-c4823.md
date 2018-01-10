---
title: "Ошибка компилятора предупреждение (уровень 3) C4823 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4823
dev_langs: C++
helpviewer_keywords: C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 18e041bd9a013779a37dc2460b8e1913b69d734b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4823"></a>Предупреждение компилятора (уровень 3) C4823
«функция»: использует закрепленные указатели, но очистки семантику не включены. Рассмотрите возможность использования/EHa  
  
Чтобы отменить закрепление объекта в управляемой куче, на который указывает закрепляющий указатель, определенный в области видимости блока, компилятор имитирует поведение деструкторов локальных классов «представим», что закрепляющий указатель имеет деструктор, который. Чтобы обеспечить вызов деструктора после возникновения исключения, необходимо включить очистку объектов, что можно сделать с помощью [/EHsc](../../build/reference/eh-exception-handling-model.md).  
  
Можно также вручную отменить закрепление объекта и пропустить это предупреждение.  
  
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
