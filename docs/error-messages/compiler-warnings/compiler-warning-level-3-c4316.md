---
title: Предупреждение компилятора (уровень 3) C4316
description: Описание предупреждения компилятора C++ C4316
ms.date: 11/04/2016
f1_keywords:
- C4316
helpviewer_keywords:
- C4316
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
ms.openlocfilehash: 3cb512aa9b851f3b3b26f7a50854a4d887087e81
ms.sourcegitcommit: 8caaf5e00aeb727741a273aecafa15de293426cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "91806565"
---
# <a name="compiler-warning-level-3-c4316"></a>Предупреждение компилятора (уровень 3) C4316

Объект, выделенный в куче, не может быть согласован для этого типа.

Выделенный с помощью объекта объект с превышением выравнивания `operator new` может не иметь указанного выравнивания. Переопределите [оператор New](../../c-runtime-library/new-operator-crt.md) и [оператор DELETE](../../c-runtime-library/delete-operator-crt.md) для перенаправленных типов, чтобы они использовали согласованные подпрограммы выделения, например [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) и [_aligned_free](../../c-runtime-library/reference/aligned-free.md). Следующий пример приводит к возникновению ошибки C4316:

```cpp
// C4316.cpp
// Test: cl /W3 /c C4316.cpp

__declspec(align(32)) struct S {}; // C4324

int main() {
    new S; // C4316
}
```
