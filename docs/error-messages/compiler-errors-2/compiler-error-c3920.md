---
title: Ошибка компилятора C3920
ms.date: 11/04/2016
f1_keywords:
- C3920
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
ms.openlocfilehash: e3c37cba4b7df2df9e9784b3a1afb8dbf9c8e8d9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491732"
---
# <a name="compiler-error-c3920"></a>Ошибка компилятора C3920

"оператор": не удается определить постфиксного инкремента или декремента WinRT или CLR оператор вызове постфиксного оператора WinRT или CLR будет вызов соответствующего префиксного WinRT или CLR operator (op_Increment/op_Decrement), но с постфиксной семантикой

Среда выполнения Windows и среда CLR не поддерживают постфиксный оператор, а пользовательские постфиксные операторы не разрешены.  Можно определить префиксный оператор, который будет использоваться для операций до и после приращения.

В следующем примере показано возникновение ошибки C3920 и приводятся сведения по ее устранению.

```
// C3920.cpp
// compile with: /clr /LD
public value struct V {
   static V operator ++(V me, int)
   // try the following line instead
   // static V operator ++(V me)
   {   // C3920
      me.m_i++;
      return me;
   }

   int m_i;
};

```