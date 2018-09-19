---
title: Ошибка компилятора C2758 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2758
dev_langs:
- C++
helpviewer_keywords:
- C2758
ms.assetid: 1d273034-194c-4926-9869-142d1b219cbe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ffa6d33dba70a463d789f3b0f016dc1d157eb65
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072931"
---
# <a name="compiler-error-c2758"></a>Ошибка компилятора C2758

member: требуется инициализация члена ссылочного типа

Ошибка компилятора C2758 возникает, если конструктор не инициализирует член ссылочного типа в списке инициализаторов. Компилятор оставляет член неопределенным. Переменные ссылочного члена должны инициализироваться при объявлении или получать значение в списке инициализации конструктора.

Следующий пример приводит к возникновению ошибки C2758:

```
// C2758.cpp
// Compile by using: cl /W3 /c C2758.cpp
struct A {
   const int i;

   A(int n) { };   // C2758
   // try the following line instead
   // A(int n) : i{n} {};
};
```