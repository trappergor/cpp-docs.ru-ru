---
title: Ошибка компилятора C2507 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2507
dev_langs:
- C++
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16cc9c5f21618f3b681fbefbfadfd66b0219d5ac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022725"
---
# <a name="compiler-error-c2507"></a>Ошибка компилятора C2507

«Идентификатор»: слишком много виртуальных модификаторов для базового класса

Класс или структура объявляется как `virtual` более одного раза. Только один `virtual` модификатор может отображаться для каждого класса в списке базовых классов.

Следующий пример приводит к возникновению ошибки C2507:

```
// C2507.cpp
// compile with: /c
class A {};
class B : virtual virtual public A {};   // C2507
class C : virtual public A {};   // OK
```