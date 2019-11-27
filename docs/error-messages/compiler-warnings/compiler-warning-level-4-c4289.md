---
title: Предупреждение компилятора (уровень 1) C4289
ms.date: 11/04/2016
f1_keywords:
- C4289
helpviewer_keywords:
- C4289
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
ms.openlocfilehash: cc1a22065be6d5f7f49d6c32f6bc9b6479399e29
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541969"
---
# <a name="compiler-warning-level-4-c4289"></a>Предупреждение компилятора (уровень 1) C4289

использовано нестандартное расширение : "переменная" : переменная управления циклом, объявленная в цикле for, используется вне области видимости этого цикла

При компиляции с параметром [/Ze](../../build/reference/za-ze-disable-language-extensions.md) и **/Zc: forScope-** переменная, объявленная в цикле [for](../../cpp/for-statement-cpp.md) **, была**использована после области действия цикла.

Сведения о том, как задать стандартное поведение в циклах **for** с параметром **/Ze**, см. в разделе [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) .

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