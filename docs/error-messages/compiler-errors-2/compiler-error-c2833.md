---
title: Ошибка компилятора C2833
ms.date: 11/04/2016
f1_keywords:
- C2833
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
ms.openlocfilehash: a6ffcb13d04f3c7c5ac62e147a2b6b2b305e11e1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218173"
---
# <a name="compiler-error-c2833"></a>Ошибка компилятора C2833

> оператор "operator *-Name*" не является распознаваемым оператором или типом

После слова **`operator`** должно следовать *имя оператора* , которое требуется переопределить, или тип, который требуется преобразовать.

Список операторов, которые можно определить в управляемом типе, см. в разделе [определяемые пользователем операторы](../../dotnet/user-defined-operators-cpp-cli.md).

Следующий пример приводит к возникновению ошибки C2833:

```cpp
// C2833.cpp
// compile with: /c
class A {};

void operator ::* ();   // C2833
void operator :: ();   // OK
```
