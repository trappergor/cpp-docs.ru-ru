---
title: Ошибка компилятора C3161
ms.date: 11/04/2016
f1_keywords:
- C3161
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
ms.openlocfilehash: 7315dad7959cdd3b950ed814b13be3867399d332
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761820"
---
# <a name="compiler-error-c3161"></a>Ошибка компилятора C3161

"Interface": недопустимый вложенный класс, структура, объединение или интерфейс в интерфейсе; Недопустимый вложенный интерфейс в классе, структуре или объединении

[__Interface](../../cpp/interface.md) может находиться только в глобальной области видимости или в пространстве имен. Класс, структура или объединение не могут присутствовать в интерфейсе.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3161.

```cpp
// C3161.cpp
// compile with: /c
__interface X {
   __interface Y {};   // C3161 A nested interface
};
```
