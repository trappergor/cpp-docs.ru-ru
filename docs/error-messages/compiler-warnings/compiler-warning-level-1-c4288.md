---
title: Предупреждение компилятора (уровень 1) C4288
ms.date: 11/04/2016
f1_keywords:
- C4288
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
ms.openlocfilehash: 81094bf019060b56337347f7d364ead7c78c8128
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626660"
---
# <a name="compiler-warning-level-1-c4288"></a>Предупреждение компилятора (уровень 1) C4288

нестандартное расширение: "var": переменная управления циклом, объявленная в цикле for, используется вне области действия цикла. он конфликтует с объявлением во внешней области видимости

При компиляции с параметром [/Ze](../../build/reference/za-ze-disable-language-extensions.md) и **/Zc: forScope-** переменная, объявленная в цикле **for** [, была](../../cpp/for-statement-cpp.md)использована после области действия цикла. Расширение Майкрософт для C++ языка позволяет этой переменной остаться в области, а C4288 напоминает, что первое объявление переменной не используется.

Сведения о том, как указать расширение Майкрософт в **for** Loops with параметром/Ze., см. в разделе [/Zc: forScope.](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)

Следующий пример приводит к возникновению ошибки C4288:

```cpp
// C4288.cpp
// compile with: /W1 /c /Zc:forScope-
int main() {
   int i = 0;    // not used in this program
   for (int i = 0 ; ; ) ;
   i++;   // C4288 using for-loop declaration of i
}
```