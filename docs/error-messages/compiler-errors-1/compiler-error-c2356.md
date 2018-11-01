---
title: Ошибка компилятора C2356
ms.date: 11/04/2016
f1_keywords:
- C2356
helpviewer_keywords:
- C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
ms.openlocfilehash: 0166cce6011017b8a18821666083f7c47f58b7a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508117"
---
# <a name="compiler-error-c2356"></a>Ошибка компилятора C2356

сегмент инициализации не должен изменяться во время преобразования

Возможные причины:

- `#pragma init_seg` предшествует код инициализации сегмента

- `#pragma init_seg` предшествует другая директива `#pragma init_seg`

Чтобы устранить проблему, переместите код инициализации сегмента в начало модуля. Если необходимо инициализировать несколько областей, переместите их в разные модули.

Следующий пример приводит к возникновению ошибки C2356:

```
// C2356.cpp
#pragma warning(disable : 4075)

int __cdecl myexit(void (__cdecl *)());
int __cdecl myexit2(void (__cdecl *)());

#pragma init_seg(".mine$m",myexit)
#pragma init_seg(".mine$m",myexit2)   // C2356
```