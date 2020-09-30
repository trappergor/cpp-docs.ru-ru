---
title: Ошибка компилятора C3369
ms.date: 11/04/2016
f1_keywords:
- C3369
helpviewer_keywords:
- C3369
ms.assetid: c6ceb9cb-3df9-4334-9a5c-d16db351d476
ms.openlocfilehash: 3b2e6f38e93514154b20e674139a2d771dcf586e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503235"
---
# <a name="compiler-error-c3369"></a>Ошибка компилятора C3369

"имя_модуля": idl_module уже определен

Использование [idl_module](../../windows/attributes/idl-module.md) там, где определяется библиотека DLL, допустимо только один раз в программе.

При компиляции следующего примера возникнет ошибка C3369:

```cpp
// C3369.cpp
// compile with: /c
[idl_module(name="name1", dllname="x.dll")]; // C3369
[idl_module(name="name1", dllname="x.dll")];
```
