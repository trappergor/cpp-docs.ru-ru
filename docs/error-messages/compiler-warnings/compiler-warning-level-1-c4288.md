---
title: Предупреждение компилятора (уровень 1) C4288
ms.date: 11/04/2016
f1_keywords:
- C4288
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
ms.openlocfilehash: d8769f5663ca0bde9048e52d4579012dfccab0a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532032"
---
# <a name="compiler-warning-level-1-c4288"></a>Предупреждение компилятора (уровень 1) C4288

использовано нестандартное расширение: «var»: переменная цикла, объявленная в цикле for, используется вне области цикла; это противоречит объявлению во внешней области

При компиляции с параметром [/Ze](../../build/reference/za-ze-disable-language-extensions.md) и **/Zc:forscope-**, переменной, объявленной в **для** цикл был использован после [для](../../cpp/for-statement-cpp.md)-области видимости цикла. Расширение Microsoft для языка C++ позволяет оставаться в области этой переменной, а C4288 напоминает, что первое объявление переменной не используется.

См. в разделе [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) сведения о способах указания расширения Microsoft в **для** циклы с параметром/Ze.

Следующий пример приводит к возникновению ошибки C4288:

```
// C4288.cpp
// compile with: /W1 /c /Zc:forScope-
int main() {
   int i = 0;    // not used in this program
   for (int i = 0 ; ; ) ;
   i++;   // C4288 using for-loop declaration of i
}
```