---
title: Ошибка компилятора C2504 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2504
dev_langs:
- C++
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6fb11774f65454799761913babb428dc6a471743
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054133"
---
# <a name="compiler-error-c2504"></a>Ошибка компилятора C2504

«класс»: базовый класс не определен

Базовый класс объявлен, но никогда не определен.  Возможные причины:

1. Пропущен включаемый файл.

1. Внешний базовый класс не объявлен с [extern](../../cpp/using-extern-to-specify-linkage.md).

Следующий пример приводит к возникновению ошибки C2504:

```
// C2504.cpp
// compile with: /c
class A;
class B : public A {};   // C2504
```

ХОРОШО

```
class C{};
class D : public C {};
```