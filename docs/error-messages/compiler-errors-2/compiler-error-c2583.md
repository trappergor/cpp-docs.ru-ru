---
title: Ошибка компилятора C2583
ms.date: 11/04/2016
f1_keywords:
- C2583
helpviewer_keywords:
- C2583
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
ms.openlocfilehash: b78b9dd69b701e1a66646234d4603973657e90c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366398"
---
# <a name="compiler-error-c2583"></a>Ошибка компилятора C2583

«Идентификатор»: «const или volatile» указатель «this» является недопустимым для конструкторов и деструкторов

Конструктор или деструктор был объявлен `const` или `volatile`. Это не допускается.

Следующий пример приводит к возникновению ошибки C2583:

```
// C2583.cpp
// compile with: /c
class A {
public:
   int i;
   A() const;   // C2583

   // try the following line instead
   // A();
};
```