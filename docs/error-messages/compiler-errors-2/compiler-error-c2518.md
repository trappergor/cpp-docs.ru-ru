---
title: Ошибка компилятора C2518
ms.date: 11/04/2016
f1_keywords:
- C2518
helpviewer_keywords:
- C2518
ms.assetid: a7895b47-da90-4851-ac97-18e81479595a
ms.openlocfilehash: d0a1f7bdc493a16b38dc2348097cc6cbea7ed898
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62282291"
---
# <a name="compiler-error-c2518"></a>Ошибка компилятора C2518

Ключевое слово «ключевое_слово» в списке базовых классов; игнорируется

Ключевые слова `class` и `struct` не должен отображаться в списке базовых классов.

Следующий пример приводит к возникновению ошибки C2518:

```
// C2518.cpp
// compile with: /c
class B {};
class C : public class B {};   // C2518
class D: public B {};   // OK
```