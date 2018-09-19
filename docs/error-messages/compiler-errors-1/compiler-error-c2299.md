---
title: Ошибка компилятора C2299 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2299
dev_langs:
- C++
helpviewer_keywords:
- C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4977f4a5ac81cf4c04d3b143f6f7e670a9d9279
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049622"
---
# <a name="compiler-error-c2299"></a>Ошибка компилятора C2299

«функция»: изменение поведения: явная специализация не может быть конструктором копий или оператор присваивания копированием

Эта ошибка также может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: предыдущие версии Visual C++ допускали явную специализацию для конструктора копий или оператор присваивания копии.

Чтобы устранить C2299, не вносите конструктор копии или оператор присваивания функции шаблона, но вместо нешаблонную функцию, которая принимает тип класса. Любой код, который вызывает конструктор копии или оператор присваивания, явно указав аргументы шаблона необходимо удалить аргументы шаблона.

Следующий пример приводит к возникновению ошибки C2299:

```
// C2299.cpp
// compile with: /c
class C {
   template <class T>
   C (T t);

   template <> C (const C&);   // C2299
   C (const C&);   // OK
};
```