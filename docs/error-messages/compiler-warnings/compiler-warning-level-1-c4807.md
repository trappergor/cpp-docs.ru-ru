---
title: "Предупреждение (уровень 1) C4807 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4807
dev_langs:
- C++
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af604a1a045b9dbef7b3c27f9c7aabd0040aa318
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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