---
title: Ошибка компилятора C3869
ms.date: 11/04/2016
f1_keywords:
- C3869
helpviewer_keywords:
- C3869
ms.assetid: 85b2ad72-95c1-4ed6-9761-6ef66c3802b7
ms.openlocfilehash: 1edc90c074389d6a666d3f01f6f7be424347f51a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428136"
---
# <a name="compiler-error-c3869"></a>Ошибка компилятора C3869

в ограничении gcnew отсутствует пустой параметр list «()»

`gcnew` Особых ограничений указан без с пустым списком параметров. См. в разделе [ограничений для параметров универсального типа (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md) Дополнительные сведения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3869.

```
// C3869.cpp
// compile with: /c /clr
using namespace System;
generic <typename T>
where T : gcnew   // C3869
// try the following line instead
// where T : gcnew()
ref class List {};
```