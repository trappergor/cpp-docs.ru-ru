---
title: Ошибка компилятора C2511
ms.date: 11/04/2016
f1_keywords:
- C2511
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
ms.openlocfilehash: 9d9ba48b0607e7a30b8748d4e9ae4f7025f11dea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522997"
---
# <a name="compiler-error-c2511"></a>Ошибка компилятора C2511

«Идентификатор»: перегруженная функция-член не найден в «class»

Версия функции не объявлено с указанными параметрами.  Возможные причины:

1. Функция переданы неверные параметры.

1. Параметры, переданные в неверном порядке.

1. Неверное написание имен параметров.

Следующий пример приводит к возникновению ошибки C2511:

```
// C2511.cpp
// compile with: /c
class C {
   int c_2;
   int Func(char *, char *);
};

int C::Func(char *, char *, int i) {   // C2511
// try the following line instead
// int C::Func(char *, char *) {
   return 0;
}
```