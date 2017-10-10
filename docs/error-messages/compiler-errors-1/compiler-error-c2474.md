---
title: "Ошибка компилятора C2474 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2474
dev_langs:
- C++
helpviewer_keywords:
- C2474
ms.assetid: 64e6c61e-6e77-480e-bcf0-b30a2fc482ac
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0630072032d69b5f936174945e366b20556a32d9
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2474"></a>Ошибка компилятора C2474
"ключевое_слово": отсутствует соседняя точка с запятой; может представлять ключевое слово или идентификатор  
  
 Компилятор ожидал встретить точку с запятой, ему не удалось определить ваше намерение. Добавьте точку с запятой, чтобы устранить эту ошибку.  
  
## <a name="example"></a>Пример  
 При компиляции следующего примера возникнет ошибка C2474:  
  
```  
// C2474.cpp  
// compile with: /clr /c  
  
ref class A {  
   ref class B {}  
   property int i;   // C2474 error  
};  
  
// OK  
ref class B {  
   ref class D {};  
   property int i;  
};  
  
ref class E {  
   ref class F {} property;   
   int i;  
};  
```
