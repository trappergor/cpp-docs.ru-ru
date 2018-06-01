---
title: Предупреждение компилятора C4957 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4957
dev_langs:
- C++
helpviewer_keywords:
- C4957
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 60cf1c03ace94c866b77c5340e2a04a9d8190e4d
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705222"
---
# <a name="compiler-warning-c4957"></a>Предупреждение компилятора C4957

> "*приведения*": явное приведение "*cast_from*«to»*конечный_тип*" недоступен для проверки

## <a name="remarks"></a>Примечания

В результате приведения будет создан недоступный для проверки образ.

Некоторые приведения являются безопасными (например, приведение `static_cast` вызывает выполнение пользовательских преобразований и приведение `const_cast`). При выполнении приведения [safe_cast](../../windows/safe-cast-cpp-component-extensions.md) гарантированно создается проверяемый код.

Дополнительные сведения см. в разделе [чистый и проверяемый код (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

**/CLR: safe** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017 г.

Это предупреждение выдается в качестве ошибки, и его можно отключить с помощью прагмы [warning](../../preprocessor/warning.md) или параметра компилятора [/wd](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению предупреждения C4957:

```cpp
// C4957.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4957 )
using namespace System;
int main() {
   Object ^ o = "Hello, World!";
   String ^ s = static_cast<String^>(o);   // C4957
   String ^ s2 = safe_cast<String^>(o);   // OK
}
```