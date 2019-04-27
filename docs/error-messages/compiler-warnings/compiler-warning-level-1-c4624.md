---
title: Предупреждение компилятора (уровень 1) C4624
ms.date: 11/04/2016
f1_keywords:
- C4624
helpviewer_keywords:
- C4624
ms.assetid: 14f61769-d92e-482b-9515-debd87b30a66
ms.openlocfilehash: b1a7d715057f4c6d8ada104ad07f6ad0b9c52fb2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221396"
---
# <a name="compiler-warning-level-1-c4624"></a>Предупреждение компилятора (уровень 1) C4624

derived class: не удалось создать деструктор, так как деструктор для базового класса недоступен или удален

Деструктор был недоступен или удален в базовом классе, поэтому он не был создан для производного класса. Любая попытка создать объект этого типа в стеке приведет к ошибке компилятора.

В следующем примере показано возникновение ошибки C4624 и приводятся сведения по ее устранению.

```
// C4624.cpp
// compile with: /W1 /c
class B {
// Uncomment the following line to fix.
// public:
   ~B();
};

class D : public B {};   // C4624 B's destructor not public
```