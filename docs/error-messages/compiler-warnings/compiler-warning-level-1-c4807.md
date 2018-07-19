---
title: Предупреждение (уровень 1) C4807 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4807
dev_langs:
- C++
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22710ee2b46a270e46aed7c043d4d988fcfaed62
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282367"
---
# <a name="compiler-warning-level-1-c4807"></a>Предупреждение компилятора (уровень 1) C4807
"операция": небезопасное смешение типа "тип" и битового поля со знаком типа "тип"  
  
 Это предупреждение возникает при сравнении однобитового поля со знаком с переменной `bool` . Так как однобитовое поле со знаком может содержать только значения –1 или 0, его небезопасно сравнивать с `bool`. Сочетание `bool` и однобитовых полей без знака не вызывает предупреждений, так как эти поля идентичны `bool` и могут содержать только 0 или 1.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению предупреждения C4807:  
  
```  
// C4807.cpp  
// compile with: /W1  
typedef struct bitfield {  
   signed mybit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bool b = true;  
  
   // try..  
   // int b = true;  
  
   bf.mybit = -1;  
   if (b == bf.mybit) {   // C4807  
      b = false;  
   }  
}  
```