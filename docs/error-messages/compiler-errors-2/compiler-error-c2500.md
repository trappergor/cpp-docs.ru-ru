---
title: Ошибка компилятора C2500 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2500
dev_langs:
- C++
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b7e24ca520796b63171fe63c2bf841fe8776845
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026677"
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