---
title: "Компилятор C4805 предупреждение (уровень 1) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4805
dev_langs:
- C++
helpviewer_keywords:
- C4805
ms.assetid: 99c7b7e2-272e-4ab5-8580-17c42e62e2ef
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 75fd2f4a76b4779f88bacd2f74eb0a824902890f
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4805"></a>Предупреждение компилятора (уровень 1) C4805
"операция": небезопасное смешение типа "тип" и типа "тип" в операции  
  
 Это предупреждение создается для операторов сравнения между [bool](../../cpp/bool-cpp.md) и [int](../../c-language/integer-types.md). При компиляции следующего примера будет выдано предупреждение C4805:  
  
```  
// C4805.cpp  
// compile with: /W1  
int main() {  
   int i = 1;  
   bool b = true;  
  
   if (i == b) {   // C4805, comparing bool and int variables  
   }  
}  
```
