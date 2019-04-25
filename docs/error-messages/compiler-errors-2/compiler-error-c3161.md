---
title: Ошибка компилятора C3161
ms.date: 11/04/2016
f1_keywords:
- C3161
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
ms.openlocfilehash: 22ecc176036308699c3ad7bd8c015836be910073
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174217"
---
# <a name="compiler-error-c3161"></a>Ошибка компилятора C3161

«интерфейс»: вложенный класс, структура, объединение или интерфейс в интерфейсе является недопустимым; недопустимо вложение интерфейса в класс, структуру или объединение

[__Interface](../../cpp/interface.md) может присутствовать только в глобальной области или в пространстве имен. Класс, структура или объединение не может использоваться в интерфейсе.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3161.

```
// C3161.cpp
// compile with: /c
__interface X {
   __interface Y {};   // C3161 A nested interface
};
```