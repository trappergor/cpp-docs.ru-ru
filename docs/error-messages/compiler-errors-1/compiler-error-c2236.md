---
title: Ошибка компилятора C2236
ms.date: 11/04/2016
f1_keywords:
- C2236
helpviewer_keywords:
- C2236
ms.assetid: 0b6771a7-a783-4729-9c3d-7a3339c432cc
ms.openlocfilehash: 988377d2995468c84b86872ab6f2b25f5c3df9f3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404316"
---
# <a name="compiler-error-c2236"></a>Ошибка компилятора C2236

Непредвиденный токен identifier. Возможно, вы забыли «;»?

Идентификатор уже определен как тип и не может быть переопределен типом, определяемым пользователем.

Следующий пример приводит к возникновению ошибки C2236:

```
// C2236.cpp
// compile with: /c
int class A {};  // C2236 "int class" is unexpected
int i;
class B {};
```