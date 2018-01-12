---
title: "Предупреждение (уровень 1) C4669 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4669
dev_langs: C++
helpviewer_keywords: C4669
ms.assetid: 97730679-e3dc-44d4-b2a8-aa65badc17f2
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8d31e2dc077ed1b86c1e246683736ceb1f827b7c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4669"></a>Предупреждение компилятора (уровень 1) C4669
cast: небезопасное преобразование: class является объектом управляемого типа или типа WinRT  
  
 Приведение содержит управляемый тип или тип среды выполнения Windows. Компилятор завершает приведение, выполняя побитовое копирование одного указателя в другой, но не выполняет другие проверки. Чтобы устранить это предупреждение, не преобразуйте классы, содержащие управляемые члены или типы среды выполнения Windows.  
  
 В следующем примере показано возникновение ошибки C4669 и приводятся сведения по ее устранению.  
  
```  
// C4669.cpp  
// compile with: /clr /W1  
ref struct A {  
   int i;  
   Object ^ pObj;   // remove the managed member to fix the warning  
};  
  
ref struct B {  
   int j;  
};  
  
int main() {  
   A ^ a = gcnew A;  
   B ^ b = reinterpret_cast<B ^>(a);   // C4669  
}  
```