---
title: Ошибка компилятора C3363
ms.date: 11/04/2016
f1_keywords:
- C3363
helpviewer_keywords:
- C3363
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
ms.openlocfilehash: eca598233dbe4cae4730e952b45945653ec8ffaa
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59775886"
---
# <a name="compiler-error-c3363"></a>Ошибка компилятора C3363

"тип": typeid можно применять только к типу

Неправильно использован оператор [typeid](../../extensions/typeid-cpp-component-extensions.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3363:

```
// C3363.cpp
// compile with: /clr
int main() {
   System::typeid;   // C3363
}
```