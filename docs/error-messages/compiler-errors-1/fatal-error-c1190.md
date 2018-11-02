---
title: Неустранимая ошибка C1190
ms.date: 11/04/2016
f1_keywords:
- C1190
helpviewer_keywords:
- C1190
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
ms.openlocfilehash: 8bd0332770dd0771ac7a02574185a506cf6fd416
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621342"
---
# <a name="fatal-error-c1190"></a>Неустранимая ошибка C1190

для управляемого целевого кода требуется параметр /clr

Вы используете конструкции среды CLR, но не указали **/clr**.

Для получения дополнительной информации см. [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md).

Следующий пример приводит к возникновению ошибки C1190:

```
// C1190.cpp
// compile with: /c
__gc class A {};   // C1190
ref class A {};
```