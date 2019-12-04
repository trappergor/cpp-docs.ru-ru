---
title: Ошибка компилятора C3363
ms.date: 11/04/2016
f1_keywords:
- C3363
helpviewer_keywords:
- C3363
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
ms.openlocfilehash: 44b41dd706c7eb290c71d7312464d688cbcf08d3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757362"
---
# <a name="compiler-error-c3363"></a>Ошибка компилятора C3363

"тип": typeid можно применять только к типу

Неправильно использован оператор [typeid](../../extensions/typeid-cpp-component-extensions.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3363:

```cpp
// C3363.cpp
// compile with: /clr
int main() {
   System::typeid;   // C3363
}
```
