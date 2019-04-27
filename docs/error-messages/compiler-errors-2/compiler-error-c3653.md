---
title: Ошибка компилятора C3653
ms.date: 11/04/2016
f1_keywords:
- C3653
helpviewer_keywords:
- C3653
ms.assetid: 316549d7-f7ef-4578-a2ba-57adc8aac527
ms.openlocfilehash: 75e2c061190b24019491db7a625ecafb5ac82b6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227517"
---
# <a name="compiler-error-c3653"></a>Ошибка компилятора C3653

«функция»: нельзя использовать в качестве именованного переопределения: переопределяемая функция не найдена; Возможно, вы забыли имя функции явно, используя:: оператор?

Явное переопределение указана функция, не найден ни в одном интерфейсе. Дополнительные сведения см. в разделе [явное переопределение](../../extensions/explicit-overrides-cpp-component-extensions.md).

Следующий пример приводит к возникновению ошибки C3653:

```
// C3653.cpp
// compile with: /clr
public interface struct I {
   void h();
};

public ref struct X : public I {
   virtual void f() new sealed = J {};   // C3653 no J in scope
   virtual void g() {}   // OK
   virtual void h() new sealed = I::h {};   // OK
};
```