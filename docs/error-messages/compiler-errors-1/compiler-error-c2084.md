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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 653dc7a4a5d330efc89942fbe4ddd07bff81f770
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2084"></a>Ошибка компилятора C2084
функция "*функция*" уже имеет тело  
  
 Функция уже определено.  
  
 В версиях Visual C++ до Visual Studio 2002  
  
-   Компилятор мог принимать несколько специализаций шаблонов, которые разрешаются в одному фактическому типу, хотя дополнительные определения никогда не будет доступен. Теперь компилятор обнаруживает эти несколько определений.  
  
-   `__int32`и `int` отсутствуют, рассматриваются как отдельные типы. Теперь компилятор считает `__int32` синонимом `int`. Это означает, что компилятор обнаружил несколько определений, если функция перегружена на обоих `__int32` и `int` и выдает ошибку.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2084:  
  
```cpp  
// C2084.cpp  
void Func(int);  
void Func(int) {}   // define function  
void Func(int) {}   // C2084 second definition  
```  
  
Чтобы исправить эту ошибку, удалите повторное определение:  
  
```  
// C2084b.cpp  
// compile with: /c  
void Func(int);  
void Func(int) {}  
```
