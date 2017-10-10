---
title: "Ошибка компилятора C2513 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2513
dev_langs:
- C++
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7eb4e7c63821f449bf9677cb5fe03c448bbbc6ee
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2513"></a>Ошибка компилятора C2513
«Тип»: нет переменных, объявленных перед «=»  
  
 Спецификатор типа в объявлении не имеет идентификатора переменной.  
  
 Следующий пример приводит к возникновению ошибки C2513:  
  
```  
// C2513.cpp  
int main() {  
   int = 9;   // C2513  
   int i = 9;   // OK  
}  
```  
  
 Эта ошибка может также возникать в результате изменений работы компилятора в Visual Studio .NET 2003: инициализация typedef больше не допускается. Инициализация typedef не допускается в соответствии со стандартом и теперь приводит к ошибке компилятора.  
  
```  
// C2513b.cpp  
// compile with: /c  
typedef struct S {  
   int m_i;  
} S = { 1 };   // C2513  
// try the following line instead  
// } S;  
```  
  
 Альтернативы можно удалить `typedef` определить переменную с помощью списка составных инициализаторов, однако это не рекомендуется, поскольку создает переменную с тем же именем, что и тип и скрыть имя типа.
