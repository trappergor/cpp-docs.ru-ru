---
title: Предупреждение компилятора (уровень 1) C4074
ms.date: 11/04/2016
f1_keywords:
- C4074
helpviewer_keywords:
- C4074
ms.assetid: cd510e66-c338-4a86-a4d7-bfa1df9b16c3
ms.openlocfilehash: 1c84bbf436354ed672cedf13358837e298c7e4a5
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626919"
---
# <a name="compiler-warning-level-1-c4074"></a>Предупреждение компилятора (уровень 1) C4074

инициализаторы, помещаемые в зарезервированную область инициализации компилятора

Область инициализации компилятора, заданная [#pragma init_seg](../../preprocessor/init-seg.md), зарезервирована корпорацией Майкрософт. Код в этой области может быть выполнен до инициализации библиотеки времени выполнения C.

Следующий пример приводит к возникновению ошибки C4074:

```cpp
// C4074.cpp
// compile with: /W1
#pragma init_seg( compiler )   // C4074

// try this line to resolve the warning
// #pragma init_seg(user)

int main() {
}
```