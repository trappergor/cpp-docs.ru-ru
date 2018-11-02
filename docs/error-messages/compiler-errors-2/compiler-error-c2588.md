---
title: Ошибка компилятора C2588
ms.date: 11/04/2016
f1_keywords:
- C2588
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
ms.openlocfilehash: 15f9ba62751d9b3cb17ab56659310292dab41adf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596785"
---
# <a name="compiler-error-c2588"></a>Ошибка компилятора C2588

":: ~ идентификатор": недопустимый глобальный деструктор

Деструктор определен не для отличных от класса, структуры или объединения. Это не допускается.

Эта ошибка может быть вызвана отсутствующий класс, структуру или объединение имени в левой области разрешения (`::`) оператор.

Следующий пример приводит к возникновению ошибки C2588:

```
// C2588.cpp
~F();   // C2588
```