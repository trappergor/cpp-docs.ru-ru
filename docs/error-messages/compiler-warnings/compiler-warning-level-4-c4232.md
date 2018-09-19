---
title: Предупреждение компилятора (уровень 4) C4232 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4232
dev_langs:
- C++
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 450c764cfc130acf28e3edfb40fcd17c8ac3b664
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118290"
---
# <a name="compiler-warning-level-4-c4232"></a>Предупреждение компилятора (уровень 4) C4232

использовано нестандартное расширение: «идентификатор»: адрес dllimport «dllimport» не является статическим, идентичность не гарантируется

Расширения Microsoft (/Ze), можно передать нестатическое значение как адрес функции, объявленные с **dllimport** модификатор. В режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), это приводит к ошибке.

Следующий пример приводит к возникновению ошибки C4232:

```
// C4232.c
// compile with: /W4 /Ze /c
int __declspec(dllimport) f();
int (*pfunc)() = &f;   // C4232
```