---
title: Предупреждение (уровень 1) C4630 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4630
dev_langs:
- C++
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d3db4e42e4bd54e1d2bd5af0eb6b19ce0fea1e2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4630"></a>Предупреждение компилятора (уровень 1) C4630
«символ»: спецификатор класса хранения «extern» недопустим для определения члена  
  
 Элемент данных или функция-член определяется как `extern`. Члены не могут быть внешними, несмотря на то, что все объекты можно. Компилятор игнорирует `extern` ключевое слово. Следующий пример приводит к возникновению ошибки C4630:  
  
```  
// C4630.cpp  
// compile with: /W1 /LD  
class A {  
   void func();  
};  
  
extern void A::func() {   // C4630, remove 'extern' to resolve  
}  
```