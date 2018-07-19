---
title: Ошибка компилятора предупреждение (уровень 3) C4823 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4823
dev_langs:
- C++
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c29499a82601dcf653ff2f003441935f1d6841a6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293235"
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
