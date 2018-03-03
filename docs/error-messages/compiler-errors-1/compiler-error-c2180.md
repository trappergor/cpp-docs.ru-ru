---
title: "Ошибка компилятора C2180 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2180
dev_langs:
- C++
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fdea36a8c6c7bf5e561c161dc7180ab3b563c0ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2180"></a>Ошибка компилятора C2180
управляющее выражение имеет тип type  
  
 Управляющее выражение в `if`, `while`, `for` или инструкция `do` — это выражение, приведенное к `void`. Чтобы устранить эту проблему, измените управляющее выражение на то, что создает `bool` или тип, который можно преобразовать в `bool`.  
  
 Следующий пример приводит к возникновению ошибки C2180:  
  
```  
// C2180.c  
  
int main() {  
   while ((void)1)   // C2180  
      return 1;  
   while (1)         // OK  
      return 0;  
}  
```