---
title: Ошибка компилятора C2838
ms.date: 11/04/2016
f1_keywords:
- C2838
helpviewer_keywords:
- C2838
ms.assetid: 176b2ad6-7a84-4019-b97e-328866054457
ms.openlocfilehash: 1482efa8b018914a4ebc509464622726ae9ebb20
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560394"
---
# <a name="compiler-error-c2838"></a>Ошибка компилятора C2838

«член»: Недопустимое полное имя в объявлении члена

Класс, структура или объединение использует полное доменное имя для повторного объявления члена другого класса, структуры или объединения.

Следующий пример приводит к возникновению ошибки C2838:

```
// C2838.cpp
// compile with: /c
class Bellini {
public:
    void Norma();
};

class Bottesini {
   Bellini::Norma();  // C2838
};
```