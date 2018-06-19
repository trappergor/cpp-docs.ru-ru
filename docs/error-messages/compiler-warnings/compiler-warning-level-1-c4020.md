---
title: Предупреждение (уровень 1) C4020 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4020
dev_langs:
- C++
helpviewer_keywords:
- C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0bb7926e22802178ff3cbcb710fbc9b74e7138f4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274571"
---
# <a name="compiler-warning-level-1-c4020"></a>Предупреждение (уровень 1) C4020 компилятора
«функция»: слишком много фактических параметров  
  
 Число фактических параметров в вызове функции превышает количество формальных параметров в прототипе или определении функции. Компилятор передает избыточные фактические параметры в соответствии с соглашением о вызовах функции.  
  
 Следующий пример приводит к возникновению ошибки C4020:  
  
```  
// C4020.c  
// compile with: /W1 /c  
void f(int);  
int main() {  
   f(1,2);   // C4020  
}  
```  
  
 Возможное решение  
  
```  
// C4020b.c  
// compile with: /c  
void f(int);  
int main() {  
   f(1);  
}  
```