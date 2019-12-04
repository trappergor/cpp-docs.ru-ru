---
title: Ошибка компилятора C2833
ms.date: 11/04/2016
f1_keywords:
- C2833
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
ms.openlocfilehash: c1467a3c67cccf28cc6b9bd0f987fe77b8da8988
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757882"
---
# <a name="compiler-error-c2833"></a>Ошибка компилятора C2833

оператор "operator" не является распознаваемым оператором или типом

После слова `operator` должен следовать оператор, который требуется переопределить, или тип, который требуется преобразовать.

Список операторов, которые можно определить в управляемом типе, см. в разделе [определяемые пользователем операторы](../../dotnet/user-defined-operators-cpp-cli.md).

Следующий пример приводит к возникновению ошибки C2833:

```cpp
// C2833.cpp
// compile with: /c
class A {};

void operator ::* ();   // C2833
void operator :: ();   // OK
```
