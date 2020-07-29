---
title: Предупреждение компилятора (уровень 1) C4289
ms.date: 11/04/2016
f1_keywords:
- C4289
helpviewer_keywords:
- C4289
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
ms.openlocfilehash: 8742fd5e64f2ba1877fa3fbecfb221ef295d463e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219902"
---
# <a name="compiler-warning-level-4-c4289"></a>Предупреждение компилятора (уровень 1) C4289

использовано нестандартное расширение : "переменная" : переменная управления циклом, объявленная в цикле for, используется вне области видимости этого цикла

При компиляции с параметром [/Ze](../../build/reference/za-ze-disable-language-extensions.md) и **/Zc: forScope-** переменная, объявленная в цикле [for](../../cpp/for-statement-cpp.md) , использовалась после **`for`** области действия цикла.

Сведения [/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) об указании стандартного поведения в **`for`** циклах с параметром **/Ze**см. в разделе/Zc: forScope.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Следующий пример приводит к возникновению ошибки C4289:

```cpp
// C4289.cpp
// compile with: /W4 /Zc:forScope-
#pragma warning(default:4289)
int main() {
   for (int i = 0 ; ; )   // C4289
      break;
   i++;
}
```
