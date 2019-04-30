---
title: Компилятор предупреждение (уровень 3) C4316
ms.date: 11/04/2016
f1_keywords:
- C4316
helpviewer_keywords:
- C4316
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
ms.openlocfilehash: 5f895a231c8b32d76e4ccd3c15ffae5717d8017f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402051"
---
# <a name="compiler-warning-level-3-c4316"></a>Компилятор предупреждение (уровень 3) C4316

Объект, размещенный в куче может быть не выровнен для данного типа.

Сверх-выровненный объект, выделенный с помощью `operator new` может не иметь заданного выравнивания. Переопределить [оператор new](../../c-runtime-library/operator-new-crt.md) и [оператор delete](../../c-runtime-library/operator-delete-crt.md) для чрезмерно выровненных типов, чтобы они использовали процедуры выровненного выделения, например, [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) и [_aligned_free](../../c-runtime-library/reference/aligned-free.md). Следующий пример приводит к возникновению ошибки C4316:

```cpp
// C4316.cpp
// Test: cl /W3 /c C4316.cpp

__declspec(align(32)) struct S {}; // C4324

int main() {
    new S; // C4316
}
```