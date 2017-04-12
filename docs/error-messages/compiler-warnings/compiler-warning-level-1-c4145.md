---
title: "Компилятор C4145 предупреждение (уровень 1) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4145
dev_langs:
- C++
helpviewer_keywords:
- C4145
ms.assetid: 0440777a-cca2-4159-aff5-e67a254ad64a
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
ms.openlocfilehash: bab140f13f3244070a9f0b6511df99957f203186
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4145"></a>Предупреждение компилятора (уровень 1) C4145
"выражение1": использование выражения с оператором отношения в качестве выражения для выбора вариантов; возможное смешение с "выражение2"  
  
 Оператор `switch` использует выражение отношения в качестве управляющего, результатом вычисления которого является логическое значение для операторов **case** . Вы имели в виду *выражение2*?  
  
## <a name="example"></a>Пример  
 При компиляции следующего примера будет выдано предупреждение C4145:  
  
```  
// C4145.cpp  
// compile with: /W1  
int main() {  
   int i = 0;  
   switch(i == 1) {   // C4145, use i instead of i == 1 to resolve  
      case 1:  
         break;  
      default:  
         break;  
   }  
}  
```
