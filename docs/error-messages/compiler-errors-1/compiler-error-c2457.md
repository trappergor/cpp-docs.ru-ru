---
title: Ошибка компилятора C2457 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2457
dev_langs:
- C++
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 61cdb4f4b679bab858717a6fb96838f389822a6b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33224927"
---
# <a name="compiler-error-c2457"></a>Ошибка компилятора C2457

> "*макрос*": предопределенный макрос не может находиться вне тела функции

Предпринята попытка использования предопределенного макроса, таких как [ &#95; &#95;ФУНКЦИЯ&#95;&#95;](../../preprocessor/predefined-macros.md), в глобальном пространстве.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2457 и также показано правильное использование:

```cpp
// C2457.cpp
#include <stdio.h>

__FUNCTION__;   // C2457, cannot be global

int main()
{
    printf_s("\n%s", __FUNCTION__);   // OK
}
```