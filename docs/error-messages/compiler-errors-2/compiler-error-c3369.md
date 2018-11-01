---
title: Ошибка компилятора C3369
ms.date: 11/04/2016
f1_keywords:
- C3369
helpviewer_keywords:
- C3369
ms.assetid: c6ceb9cb-3df9-4334-9a5c-d16db351d476
ms.openlocfilehash: 0cd27da4b73732513afe0bd33a2d7312e6ddbe97
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618963"
---
# <a name="compiler-error-c3369"></a>Ошибка компилятора C3369

"имя_модуля": idl_module уже определен

Использование [idl_module](../../windows/idl-module.md) там, где определяется библиотека DLL, допустимо только один раз в программе.

При компиляции следующего примера возникнет ошибка C3369:

```
// C3369.cpp
// compile with: /c
[idl_module(name="name1", dllname="x.dll")]; // C3369
[idl_module(name="name1", dllname="x.dll")];
```