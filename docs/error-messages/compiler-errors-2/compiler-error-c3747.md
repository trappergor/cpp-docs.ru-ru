---
title: Ошибка компилятора C3747 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3747
dev_langs:
- C++
helpviewer_keywords:
- C3747
ms.assetid: a9a4be67-5d9c-4dcc-9ae9-baae46cbecde
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1f657e6d3f64a4d8a2244ab2927a9a712c14b1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091677"
---
# <a name="compiler-error-c3747"></a>Ошибка компилятора C3747

отсутствует параметр типа по умолчанию: параметр param

Параметры универсального класса или шаблона со значениями по умолчанию не может следовать в списке параметров по параметрам, у которых нет значения по умолчанию.

Следующий пример приводит к возникновению ошибки C3747:

```
// C3747.cpp
template <class T1 = int, class T2>   // C3747
struct MyStruct {};
```

Возможное решение

```
// C3747b.cpp
// compile with: /c
template <class T1, class T2 = int>
struct MyStruct {};
```