---
title: "Ошибка компилятора C2274 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2274
dev_langs: C++
helpviewer_keywords: C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4315d1cfef9a0583b1f44c8caa264378e32f1a35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2274"></a>Ошибка компилятора C2274
«Тип»: недопустимо в качестве правой стороны '.' оператор  
  
 Тип отображается как правый операнд оператора доступа к членам (.).  
  
 Эта ошибка может быть вызвано при обращении к преобразования определяемого пользователем типа. Используйте ключевое слово `operator` между период и `type`.  
  
 При компиляции следующего примера возникнет ошибка C2286:  
  
```  
// C2274.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
  
int main() {  
   MyClass ClassName;  
   int i = ClassName.int();   // C2274  
   int j = ClassName.operator int();   // OK  
}  
```