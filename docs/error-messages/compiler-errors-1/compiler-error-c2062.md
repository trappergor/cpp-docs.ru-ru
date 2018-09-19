---
title: Ошибка компилятора C2062 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2062
dev_langs:
- C++
helpviewer_keywords:
- C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbda0894b25e09681207d6447bb40727d490fc02
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072255"
---
# <a name="compiler-error-c2062"></a>Ошибка компилятора C2062

Тип «тип» непредвиденный

Компилятор не ожидала имени типа.

Следующий пример приводит к возникновению ошибки C2062:

```
// C2062.cpp
// compile with: /c
struct A {  : int l; };   // C2062
struct B { private: int l; };   // OK
```

C2062 также может возникать из-за способа компилятор обрабатывает неопределенные типы в списке параметров конструктора. Если компилятор обнаруживает неопределенный тип (с опечаткой?), предполагается конструктор — это выражение и выдает C2062. Чтобы решить, используйте только определенные типы в списке параметров конструктора.