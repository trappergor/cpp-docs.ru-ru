---
title: Ошибка компилятора C3139
ms.date: 11/04/2016
f1_keywords:
- C3139
helpviewer_keywords:
- C3139
ms.assetid: 95c92263-10ac-4ff3-b385-6312dd92adbc
ms.openlocfilehash: 86f905653c6e1574a1d1c0a1225294b3a4dc5f3e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506174"
---
# <a name="compiler-error-c3139"></a>Ошибка компилятора C3139

"struct": невозможно экспортировать определяемый пользователем тип без членов

Предпринята попытка применить атрибут [экспорта](../../windows/attributes/export.md) к ПУСТому определяемому пользователем типу (определяемому типом). Пример:

```cpp
// C3139.cpp
#include "unknwn.h"
[emitidl];
[module(name=xx)];

[export] struct MyStruct {   // C3139 empty type
};
int main(){}
```
