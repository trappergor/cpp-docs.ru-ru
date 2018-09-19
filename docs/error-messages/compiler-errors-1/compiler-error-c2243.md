---
title: Ошибка компилятора C2243 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2243
dev_langs:
- C++
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef5d3a6c20ff147ac2a4b765c7779cec9f19627e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102233"
---
# <a name="compiler-error-c2243"></a>Ошибка компилятора C2243

Преобразование conversion type из type1 в type2 существует, но недоступно

Защита доступа (`protected` или `private`) не позволила выполнить преобразование из указателя на производный класс в указатель на базовый класс.

Следующий пример приводит к возникновению ошибки C2243:

```
// C2243.cpp
// compile with: /c
class B {};
class D : private B {};
class E : public B {};

D d;
B *p = &d;   // C2243

E e;
B *p2 = &e;
```

Базовые классы с типом доступа `protected` или `private` недоступны клиентам производного класса. Эти уровни контроля доступа используются для обозначения того, что базовый класс в реализации должен быть невидим для клиентов. Используйте открытое наследование, чтобы у клиентов производного класса был доступ к неявному преобразованию указателя на производный класс в указатель на базовый класс.