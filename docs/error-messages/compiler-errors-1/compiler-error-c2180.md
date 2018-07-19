---
title: Ошибка компилятора C2180 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2180
dev_langs:
- C++
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a43c179b837e840f800a6c468efdd9cdd6a6604b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171540"
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