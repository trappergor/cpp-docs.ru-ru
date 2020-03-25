---
title: Ошибка компилятора C2457
ms.date: 11/04/2016
f1_keywords:
- C2457
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
ms.openlocfilehash: 40e666b1f2b566ca6309ee7759452647f8101a38
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205248"
---
# <a name="compiler-error-c2457"></a>Ошибка компилятора C2457

> "*макрос*": предопределенный макрос не может находиться за пределами тела функции

Предпринята попытка использования предопределенного макроса, например [ &#95; &#95;функции&#95;](../../preprocessor/predefined-macros.md), в глобальном пространстве.

## <a name="example"></a>Пример

В следующем примере показано создание C2457, а также правильное использование:

```cpp
// C2457.cpp
#include <stdio.h>

__FUNCTION__;   // C2457, cannot be global

int main()
{
    printf_s("\n%s", __FUNCTION__);   // OK
}
```
