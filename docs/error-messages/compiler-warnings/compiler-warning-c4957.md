---
title: Предупреждение компилятора C4957
ms.date: 11/04/2016
f1_keywords:
- C4957
helpviewer_keywords:
- C4957
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
ms.openlocfilehash: 340c26c97d0b5b686eee487cd3fd8b6b05bdf373
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164914"
---
# <a name="compiler-warning-c4957"></a>Предупреждение компилятора C4957

> "*приведение*": явное приведение "*cast_from*" к "*cast_to*" не поддается проверке

## <a name="remarks"></a>Remarks

В результате приведения будет создан недоступный для проверки образ.

Некоторые приведения являются безопасными (например, приведение `static_cast` вызывает выполнение пользовательских преобразований и приведение `const_cast`). При выполнении приведения [safe_cast](../../extensions/safe-cast-cpp-component-extensions.md) гарантированно создается проверяемый код.

Дополнительные сведения см. в разделе [чистый и проверяемый кодC++(/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

Параметр компилятора **/clr: Сейф** является устаревшим в visual Studio 2015 и не поддерживается в visual Studio 2017.

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
