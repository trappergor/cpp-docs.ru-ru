---
title: Предупреждение компилятора (уровень 4) C4254 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- c4254
dev_langs:
- C++
helpviewer_keywords:
- C4254
ms.assetid: c7dcef24-d535-4c98-bb41-fc3d2b88fd11
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 039ce69f624fdcdd6beba2d6d262f920b7848687
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115942"
---
# <a name="compiler-warning-level-4-c4254"></a>Предупреждение компилятора (уровень 4) C4254

«operator»: преобразование из «тип1» в «тип2», возможна потеря данных

Крупное битовое поле было назначено меньшего размера битовое поле. Возможна потеря данных.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Следующий пример приводит к возникновению ошибки C4254:

```
// C4254.cpp
// compile with: /W4
#pragma warning(default: 4254)

struct X {
   int a : 20;
   int b : 12;
};

int main() {
   X *x = new X();
   x->b = 10;
   x->a = 4;
   x->a = x->b;    // OK
   x->b = x->a;    // C4254
};
```