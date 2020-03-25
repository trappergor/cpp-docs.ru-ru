---
title: Предупреждение компилятора (уровень 4) C4232
ms.date: 11/04/2016
f1_keywords:
- C4232
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
ms.openlocfilehash: c0e79dfa4564960a5660f0932b142b436370ac05
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173924"
---
# <a name="compiler-warning-level-4-c4232"></a>Предупреждение компилятора (уровень 4) C4232

использовано нестандартное расширение: "идентификатор": адрес dllimport "dllimport" не является статическим, удостоверение не гарантируется

В разделе расширения Майкрософт (/Ze) можно предоставить нестатическое значение в качестве адреса функции, объявленной с помощью модификатора **DllImport** . В режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) это приводит к ошибке.

Следующий пример приводит к возникновению ошибки C4232:

```c
// C4232.c
// compile with: /W4 /Ze /c
int __declspec(dllimport) f();
int (*pfunc)() = &f;   // C4232
```
