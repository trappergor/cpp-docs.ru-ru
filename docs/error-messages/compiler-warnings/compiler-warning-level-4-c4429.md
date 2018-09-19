---
title: Предупреждение компилятора (уровень 4) C4429 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4429
dev_langs:
- C++
helpviewer_keywords:
- C4429
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19e10806ffa601caa4212b5e5f98b823ec8941d0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049232"
---
# <a name="compiler-warning-level-4-c4429"></a>Предупреждение компилятора (уровень 4) C4429

Возможные неполные или неправильно сформированный универсальное имя символа

Компилятор обнаружил последовательность символов, которые могут быть неправильно сформированных универсальное имя символа. Универсальное имя символа — `\u` следуют четыре шестнадцатеричные цифры или `\U` следовать восемь шестнадцатеричных цифр.

Следующий пример приводит к возникновению ошибки C4429:

```
// C4429.cpp
// compile with: /W4 /WX
int \ug0e4 = 0;   // C4429
// Try the following line instead:
// int \u00e4 = 0;   // OK, a well-formed universal character name.
```