---
title: Ошибка компилятора C2588
ms.date: 11/04/2016
f1_keywords:
- C2588
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
ms.openlocfilehash: 15f9ba62751d9b3cb17ab56659310292dab41adf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350456"
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