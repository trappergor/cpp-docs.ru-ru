---
title: Предупреждение (уровень 4) C4289 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4289
dev_langs:
- C++
helpviewer_keywords:
- C4289
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 35cb22c767c0ea64a1536bd4d02ad8653bb94250
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102844"
---
# <a name="compiler-warning-level-4-c4289"></a>Предупреждение компилятора (уровень 1) C4289

использовано нестандартное расширение : "переменная" : переменная управления циклом, объявленная в цикле for, используется вне области видимости этого цикла

При компиляции с параметром [/Ze](../../build/reference/za-ze-disable-language-extensions.md) и **/Zc:forScope-**, переменной, объявленной в [для](../../cpp/for-statement-cpp.md) цикл был использован после **для**-области видимости цикла.

См. в разделе [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) сведения о том, как указать стандартное поведение в **для** циклы **/Ze**.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Следующий пример приводит к возникновению ошибки C4289:

```
// C4289.cpp
// compile with: /W4 /Zc:forScope-
#pragma warning(default:4289)
int main() {
   for (int i = 0 ; ; )   // C4289
      break;
   i++;
}
```