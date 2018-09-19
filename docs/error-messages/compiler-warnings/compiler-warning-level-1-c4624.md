---
title: Предупреждение компилятора (уровень 1) C4624 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4624
dev_langs:
- C++
helpviewer_keywords:
- C4624
ms.assetid: 14f61769-d92e-482b-9515-debd87b30a66
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dbc482fe693da366a3ba3ce7e53d5e8bbf23618c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118394"
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