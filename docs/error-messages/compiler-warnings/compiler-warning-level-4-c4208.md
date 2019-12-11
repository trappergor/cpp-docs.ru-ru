---
title: Предупреждение компилятора (уровень 4) C4208
ms.date: 11/04/2016
f1_keywords:
- C4208
helpviewer_keywords:
- C4208
ms.assetid: 5cb0a36e-3fb5-422f-a5f9-e40b70776c27
ms.openlocfilehash: c6e83feacd08bdb2203873a14a47ebde686a94f9
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991609"
---
# <a name="compiler-warning-level-4-c4208"></a>Предупреждение компилятора (уровень 4) C4208

использовано нестандартное расширение: Delete [exp]-exp вычислено, но пропущено

С помощью расширений Майкрософт (/Ze) можно удалить массив, используя значение в квадратных скобках с [оператором delete](../../cpp/delete-operator-cpp.md). Значение игнорируется.

```cpp
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

Такие значения недопустимы в режиме совместимости ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).
