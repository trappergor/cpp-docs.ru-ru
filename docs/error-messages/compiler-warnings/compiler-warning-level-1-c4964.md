---
title: Предупреждение компилятора (уровень 1) C4964
ms.date: 11/04/2016
f1_keywords:
- C4964
helpviewer_keywords:
- C4964
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
ms.openlocfilehash: 2a75a1b7d3738794046ac697113c3c746bb6fcff
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052244"
---
# <a name="compiler-warning-level-1-c4964"></a>Предупреждение компилятора (уровень 1) C4964

Параметры оптимизации не указаны. сведения о профиле не будут собраны

Указаны [/GL](../../build/reference/gl-whole-program-optimization.md) и [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) , но не было запрошено ни одной оптимизации, поэтому PGC-файлы не будут созданы и, следовательно, оптимизация профиля не будет возможна.

Если вы хотите, чтобы файлы. PGC создавались при запуске приложения, укажите один из параметров компилятора [/o](../../build/reference/o-options-optimize-code.md) .

Следующий пример приводит к возникновению ошибки C4964:

```cpp
// C4964.cpp
// compile with: /W1 /GL /link /ltcg:pgi
// C4964 expected
// Add /O2, for example, to the command line to resolve this warning.
int main() {
   int i;
}
```