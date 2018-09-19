---
title: Ошибка компилятора C3873 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3873
helpviewer_keywords:
- C3873
ms.assetid: e68fd3be-2391-492b-ac3f-d2428901b2e9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 83580d8202dada0b650b1703dcadf9b99e6771d9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072814"
---
# <a name="compiler-error-c3873"></a>Ошибка компилятора C3873

"char": этот символ недопустим как первый символ идентификатора

Компилятор C++ следует стандарту C ++ 11 в отношении разрешенных символов в идентификаторе. В идентификаторе можно использовать только определенные диапазоны символов и универсальных имен символов. Дополнительные ограничения применяются к начальному символу идентификатора. Дополнительные сведения и список разрешенных символов и диапазонов универсальных имен символов см. в разделе [Identifiers](../../cpp/identifiers-cpp.md).

Диапазон разрешенных символов в идентификаторе шире, чем при компиляции кода C++/CLI. Идентификаторы в коде, скомпилированном с помощью /clr, должны соответствовать  [стандарту ECMA-335: Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).

Следующий пример приводит к возникновению ошибки C3873:

```
// C3873.cpp
int main() {
   int \u036F_abc;   // C3873, not in allowed range for initial character
   int abc_\u036F;   // OK, in allowed range for non-initial character
}
```