---
title: Ошибка компилятора C2356 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2356
dev_langs:
- C++
helpviewer_keywords:
- C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8dfad1703b36e1cd995207d35b99b323c883f828
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065417"
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