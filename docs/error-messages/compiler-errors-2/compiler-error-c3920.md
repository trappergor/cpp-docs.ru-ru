---
title: Ошибка компилятора C3920
ms.date: 11/04/2016
f1_keywords:
- C3920
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
ms.openlocfilehash: d7163cf07a440a0afd1216b3e5cf665326ffb963
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386607"
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