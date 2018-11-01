---
title: Ошибка компилятора C2500
ms.date: 11/04/2016
f1_keywords:
- C2500
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
ms.openlocfilehash: a5753fc99efcdb1064a21981c62faaba84d44189
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468371"
---
# <a name="compiler-error-c2500"></a>Ошибка компилятора C2500

«идентификатор1»: «идентификатор2» уже является прямым базовым классом

Класс или структура появляется несколько раз в списке базовых классов.

Прямым базовым классом является упомянутый в списке базовых. Косвенным базовым является базовым классом одного из классов в списке базовых.

Класс нельзя использовать как прямой базовый класс более одного раза. Класс можно использовать как косвенный базовый класс более одного раза.

Следующий пример приводит к возникновению ошибки C2500:

```
// C2500.cpp
// compile with: /c
class A {};
class B : public A, public A {};    // C2500

// OK
class C : public A {};
class D : public A {};
class E : public C, public D {};
```