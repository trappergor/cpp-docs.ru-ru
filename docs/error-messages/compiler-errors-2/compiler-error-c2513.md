---
title: Ошибка компилятора C2513 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2513
dev_langs:
- C++
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82df537e49ca17140d70977486314f43a072022d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045436"
---
# <a name="compiler-error-c2513"></a>Ошибка компилятора C2513

«Тип»: нет переменных, объявленных перед «=»

Спецификатор типа в объявлении не имеет идентификатора переменной.

Следующий пример приводит к возникновению ошибки C2513:

```
// C2513.cpp
int main() {
   int = 9;   // C2513
   int i = 9;   // OK
}
```

Эта ошибка также может возникать в результате изменений работы компилятора, в Visual Studio .NET 2003: инициализация typedef не допускается. Инициализация typedef не допускается согласно стандарту и теперь приводит к ошибке компилятора.

```
// C2513b.cpp
// compile with: /c
typedef struct S {
   int m_i;
} S = { 1 };   // C2513
// try the following line instead
// } S;
```

Или же можно удалить `typedef` определить переменную с помощью списка инициализаторов статистических выражений, но это не рекомендуется, поскольку создает переменную с тем же именем, что тип и скрыть имя типа.