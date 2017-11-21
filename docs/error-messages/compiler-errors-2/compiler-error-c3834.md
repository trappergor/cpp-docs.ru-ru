---
title: "Ошибка компилятора C3834 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3834
dev_langs: C++
helpviewer_keywords: C3834
ms.assetid: 059e0dc4-300b-4e74-b6c2-41a57831fe2a
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8a827b2abe6352f083dbd21bdd9647af9b3b1f5c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3834"></a>Ошибка компилятора C3834
недопустимое явное приведение к Закрепляющему указателю; Вместо этого используйте закрепленную локальную переменную  
  
 Явное приведение указатель не допускаются.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3834.  
  
```  
// C3834.cpp  
// compile with: /clr  
int main() {  
   int x = 33;  
  
   pin_ptr<int> p = safe_cast<pin_ptr<int> >(&x);   // C3834  
   pin_ptr<int> p2 = &x;   // OK  
}  
```  
