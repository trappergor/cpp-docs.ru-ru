---
title: Ошибка компилятора C3353
ms.date: 11/04/2016
f1_keywords:
- C3353
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
ms.openlocfilehash: c38642d7abd4f2fd50792c548c9a5521b2da10ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402649"
---
# <a name="compiler-error-c3353"></a>Ошибка компилятора C3353

delegate: создание делегата допускается только из глобальной функции или функции-члена управляемого типа или типа WinRT

Делегаты, объявленные с [делегировать](../../extensions/delegate-cpp-component-extensions.md) ключевое слово, могут объявляться только в глобальной области.

Следующий пример приводит к возникновению ошибки C3353:

```
// C3353.cpp
// compile with: /clr
delegate int f;   // C3353
```