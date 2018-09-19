---
title: Ошибка компилятора C2341 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2341
dev_langs:
- C++
helpviewer_keywords:
- C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adac1e6f6e5f5d58b6091a389537a42f0e496b31
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020203"
---
# <a name="compiler-error-c2341"></a>Ошибка компилятора C2341

«имя_раздела»: сегмент должен быть определен с помощью #pragma data_seg, code_seg или предыдущего раздела, для использования

[Выделить](../../cpp/allocate.md) Инструкция ссылается на сегмент, который еще не определен [code_seg](../../preprocessor/code-seg.md), [data_seg](../../preprocessor/data-seg.md), или [разделе](../../preprocessor/section.md) директивы pragma.

Следующий пример приводит к возникновению ошибки C2341:

```
// C2341.cpp
// compile with: /c
__declspec(allocate(".test"))   // C2341
int j = 1;
```

Возможное решение

```
// C2341b.cpp
// compile with: /c
#pragma data_seg(".test")
__declspec(allocate(".test"))
int j = 1;
```