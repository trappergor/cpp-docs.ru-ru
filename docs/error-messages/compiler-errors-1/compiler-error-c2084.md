---
title: "Ошибка компилятора C2084 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2084
dev_langs:
- C++
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf9e0888e0f959d77198efe036c0234c985ea365
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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