---
title: Предупреждение компилятора (уровень 4) C4208
ms.date: 11/04/2016
f1_keywords:
- C4208
helpviewer_keywords:
- C4208
ms.assetid: 5cb0a36e-3fb5-422f-a5f9-e40b70776c27
ms.openlocfilehash: 11c6b1ad50c44ac4ad2a9d014e57efef097d9d8b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50524531"
---
# <a name="compiler-warning-level-4-c4208"></a>Предупреждение компилятора (уровень 4) C4208

использовано нестандартное расширение: delete [exp] - exp вычислено, но игнорируется

В расширениях Майкрософт (/Ze), можно удалить массив с помощью значения в скобках с [оператор delete](../../cpp/delete-operator-cpp.md). Значение учитывается.

```
// C4208.cpp
// compile with: /W4
int main()
{
   int * MyArray = new int[18];
   delete [18] MyArray;      // C4208
   MyArray = new int[18];
   delete [] MyArray;        // ok
}
```

Такие значения недопустимы в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).