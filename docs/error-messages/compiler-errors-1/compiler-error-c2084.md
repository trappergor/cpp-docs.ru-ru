---
title: "Ошибка компилятора C2084 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2084
dev_langs:
- C++
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 0ecd2db7dc5ac207d8257b725be83cdce983d5c8
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2084"></a>Ошибка компилятора C2084
функция «функция» уже имеет тело  
  
 Функция уже определено.  
  
 В предыдущих версиях Visual C++  
  
-   Компилятор мог принимать несколько специализаций шаблонов, которые разрешаются к одному фактическому типу, хотя дополнительные определения никогда не будет доступен. Теперь компилятор обнаруживает эти множественные определения.  
  
-   __int32 и int обрабатывались как отдельные типы. Теперь компилятор считает \__int32 синонимом int. Это означает, что компилятор обнаруживает несколько определений, если функция перегружена и \__int32 и int и выводит сообщение об ошибке.  
  
 Следующий пример приводит к возникновению ошибки C2084:  
  
```  
// C2084.cpp  
void Func(int);  
void Func(int) {}   // define function  
void Func(int) {}   // C2084 second definition  
```  
  
 Возможное решение:  
  
```  
// C2084b.cpp  
// compile with: /c  
void Func(int);  
void Func(int) {}  
```
