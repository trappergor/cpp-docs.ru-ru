---
title: Ошибка компилятора C2431 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2431
dev_langs:
- C++
helpviewer_keywords:
- C2431
ms.assetid: 88a5b648-c89f-47d1-a20e-63231ab4f0f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94a3f94163e02b953a4739b56a04f92f2499d27f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2431"></a>Ошибка компилятора C2431
Недопустимый индексный регистр в «идентификатор»  
  
 Регистр ESP масштабируется или использовать в качестве индекса и базовым регистром. SIB, кодировку для процессора не допускает либо x86.  
  
 Следующий пример приводит к возникновению ошибки C2431:  
  
```  
// C2431.cpp  
// processor: x86  
int main() {  
   _asm mov ax, [ESI + 2*ESP]   // C2431  
   _asm mov ax, [esp + esp]   // C2431  
}  
```