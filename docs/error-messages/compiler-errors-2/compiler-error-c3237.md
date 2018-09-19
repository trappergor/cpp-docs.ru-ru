---
title: Ошибка компилятора C3237 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3237
dev_langs:
- C++
helpviewer_keywords:
- C3237
ms.assetid: 690970c8-e13b-4ff3-96e3-5fd93c4d356b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dbfeb7775bc6d48078affcc37c2dead3c920307a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068615"
---
# <a name="compiler-error-c3237"></a>Ошибка компилятора C3237

"универсальный_класс": универсальный класс не может быть пользовательским атрибутом

Универсальные классы не могут быть пользовательскими атрибутами.

## <a name="example"></a>Пример

При компиляции следующего примера возникнет ошибка C3237.

```
// C3237.cpp
// compile with: /clr /c
// C3237 expected
using namespace System;

generic <class T>
// Delete the following line to resolve.
[attribute(AttributeTargets::All, AllowMultiple=true)]
public ref class GR {};
```