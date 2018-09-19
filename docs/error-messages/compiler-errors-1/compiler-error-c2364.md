---
title: Ошибка компилятора C2364 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2364
dev_langs:
- C++
helpviewer_keywords:
- C2364
ms.assetid: 4f550571-94b5-42ca-84cb-663fecbead44
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d35701eb47bdf633377652094b847ccdfb31e59
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100634"
---
# <a name="compiler-error-c2364"></a>Ошибка компилятора C2364

«Тип»: недопустимый тип для настраиваемого атрибута

Именованные аргументы для настраиваемых атрибутов ограничены константами времени компиляции. Например, целочисленных типов (int, char, и т.д.), System::Type ^ и System::Object ^.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2364.

```
// c2364.cpp
// compile with: /clr /c
using namespace System;

[attribute(AttributeTargets::All)]
public ref struct ABC {
public:
   // Delete the following line to resolve.
   ABC( Enum^ ) {}   // C2364
   ABC( int ) {}   // OK
};
```