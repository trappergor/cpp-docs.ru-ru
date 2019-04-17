---
title: Предупреждение компилятора C4958
ms.date: 11/04/2016
f1_keywords:
- C4958
helpviewer_keywords:
- C4958
ms.assetid: e79b9e9c-d572-4a3a-a3b6-60962b70864a
ms.openlocfilehash: 96b73975f391493340dd01d85ad30a8c888b44c0
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769411"
---
# <a name="compiler-warning-c4958"></a>Предупреждение компилятора C4958

> "*операции*": арифметика указателей не поддается проверке

## <a name="remarks"></a>Примечания

Использование арифметики указателей создает непроверяемый образ.

Дополнительные сведения см. в разделе [чистый и проверяемый код (C++выполняет)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

**/CLR: safe** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017.

Это предупреждение выдается в качестве ошибки, и его можно отключить с помощью прагмы [warning](../../preprocessor/warning.md) или параметра компилятора [/wd](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Пример

В следующем примере возникает ошибка C4958:

```cpp
// C4958.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4958 )
using namespace System;

int main( ) {
   Int32 arr[] = new Int32[10];
   Int32* p = &arr[0];
   p++;   // C4958
}
```

Компилятор реализует операции с массивами с использованием арифметики указателей. Таким образом, собственные массивы не подлежат проверке; используйте вместо них массив CLR. Дополнительные сведения см. в описании [array](../../extensions/arrays-cpp-component-extensions.md).

В следующем примере возникает ошибка C4958:

```cpp
// C4958b.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4958 )

int main() {
   int array[5];
   array[4] = 0;   // C4958
}
```