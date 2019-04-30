---
title: Ошибка компилятора C2833
ms.date: 11/04/2016
f1_keywords:
- C2833
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
ms.openlocfilehash: dad6a64f145c3d49d3b43044ea76a11d35827943
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408372"
---
# <a name="compiler-error-c2833"></a>Ошибка компилятора C2833

«оператор» не является распознаваемым оператором или типом

Слово `operator` должен следовать оператор, который вы хотите переопределить или типом, который требуется преобразовать.

Список операторов, которые можно определить в управляемом типе, см. в разделе [определяемых пользователем операторов](../../dotnet/user-defined-operators-cpp-cli.md).

Следующий пример приводит к возникновению ошибки C2833:

```
// C2833.cpp
// compile with: /c
class A {};

void operator ::* ();   // C2833
void operator :: ();   // OK
```