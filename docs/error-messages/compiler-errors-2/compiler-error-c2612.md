---
title: Ошибка компилятора C2612 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2612
dev_langs:
- C++
helpviewer_keywords:
- C2612
ms.assetid: 6faacfd6-4455-41a2-808e-0f6799f84d6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2bdc91dd2b64c4fbd3a14670ba500ac970c9ad3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135793"
---
# <a name="compiler-error-c2612"></a>Ошибка компилятора C2612

в конце «char» недопустим в списке инициализаторов базового класса или члена

Символ отображается после последнего базового класса или члена в списке инициализаторов.

Следующий пример приводит к возникновению ошибки C2612:

```
// C2612.cpp
class A {
public:
   int i;
   A( int ia ) : i( ia ) + {};   // C2612
};
```