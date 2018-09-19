---
title: Ошибка компилятора C2588 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2588
dev_langs:
- C++
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d656dbde06d6052fd10611675f2cff8818cdb6e5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108577"
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