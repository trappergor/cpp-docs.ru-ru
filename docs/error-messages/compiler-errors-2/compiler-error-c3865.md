---
title: Ошибка компилятора C3865
ms.date: 11/04/2016
f1_keywords:
- C3865
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
ms.openlocfilehash: 846657d3598e268d78ff3c39f2bfc901756ad370
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302024"
---
# <a name="compiler-error-c3865"></a>Ошибка компилятора C3865

«соглашение_о_вызовах»: может использоваться только в собственных функциях-членах

Соглашение о вызове был использован на функцию, которая была глобальной функции или функции-члена управляемого. Соглашение о вызовах может использоваться только в функции-члене собственные (не управляемые).

Дополнительные сведения см. в разделе [соглашения о вызовах](../../cpp/calling-conventions.md).

Следующий пример приводит к возникновению ошибки C3865:

```
// C3865.cpp
// compile with: /clr
// processor: x86
void __thiscall Func(){}   // C3865

// OK
struct MyType {
   void __thiscall Func(){}
};
```