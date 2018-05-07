---
title: Ошибка компилятора C2084 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2084
dev_langs:
- C++
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ce1510dd6e78b8774d3cc433f583c16cdbb8d06
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2084"></a>Ошибка компилятора C2084
функция "*функция*" уже имеет тело  
  
 Функция уже определено.  
  
 В версиях Visual C++ до Visual Studio 2002  
  
-   Компилятор мог принимать несколько специализаций шаблонов, которые разрешаются в одному фактическому типу, хотя дополнительные определения никогда не будет доступен. Теперь компилятор обнаруживает эти несколько определений.  
  
-   `__int32` и `int` отсутствуют, рассматриваются как отдельные типы. Теперь компилятор считает `__int32` синонимом `int`. Это означает, что компилятор обнаружил несколько определений, если функция перегружена на обоих `__int32` и `int` и выдает ошибку.  
  
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