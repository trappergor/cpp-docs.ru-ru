---
title: Предупреждение компилятора (уровень 4) C4429
ms.date: 11/04/2016
f1_keywords:
- C4429
helpviewer_keywords:
- C4429
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
ms.openlocfilehash: d4eb7e7075c7adf418254e748f104a6d57c72741
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391534"
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