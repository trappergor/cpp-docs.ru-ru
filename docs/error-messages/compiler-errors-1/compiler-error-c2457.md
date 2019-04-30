---
title: Ошибка компилятора C2457
ms.date: 11/04/2016
f1_keywords:
- C2457
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
ms.openlocfilehash: a08ac9f9cfbc332b90ad16c663349ee227427278
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347107"
---
# <a name="compiler-error-c2457"></a>Ошибка компилятора C2457

> "*макрос*": добавлен предустановленный макрос не может находиться вне тела функции

Предпринята попытка использования предопределенного макроса, такие как [ &#95; &#95;ФУНКЦИЯ&#95;&#95;](../../preprocessor/predefined-macros.md), в глобальном пространстве.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2457, а также показано правильное использование:

```cpp
// C2457.cpp
#include <stdio.h>

__FUNCTION__;   // C2457, cannot be global

int main()
{
    printf_s("\n%s", __FUNCTION__);   // OK
}
```