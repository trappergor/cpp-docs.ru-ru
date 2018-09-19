---
title: Ошибка компилятора C3286 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3286
dev_langs:
- C++
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ea2a6dcccd6de6d4fc3081106123f4ab37f71a2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052920"
---
# <a name="compiler-error-c3286"></a>Ошибка компилятора C3286

> "*описатель*": у переменной цикла не может иметь любой спецификаторы классов хранения

Класс хранения не может указываться для переменной итерации. Дополнительные сведения см. в разделе [классы хранения (C++)](../../cpp/storage-classes-cpp.md) и [для каждого из них в](../../dotnet/for-each-in.md).

## <a name="example"></a>Пример

В следующем примере возникает ошибка c3286: и также показано правильное использование.

```cpp
// C3286.cpp
// compile with: /clr
int main() {
   array<int> ^p = { 1, 2, 3 };
   for each (static int i in p) {}   // C3286
   for each (int j in p) {}   // OK
}
```