---
title: Предупреждение компилятора C4958 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4958
dev_langs:
- C++
helpviewer_keywords:
- C4958
ms.assetid: e79b9e9c-d572-4a3a-a3b6-60962b70864a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e32acc4ec45275976e7fb56f993b10ba8a2a855
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704877"
---
# <a name="compiler-warning-c4958"></a>Предупреждение компилятора C4958

> "*операции*": арифметика указателей не подлежит проверке.

## <a name="remarks"></a>Примечания

Использование арифметики указателей создает непроверяемый образ.

Дополнительные сведения см. в разделе [чистый и проверяемый код (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

**/CLR: safe** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017 г.

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

Компилятор реализует операции с массивами с использованием арифметики указателей. Таким образом, собственные массивы не подлежат проверке; используйте вместо них массив CLR. Дополнительные сведения см. в описании [array](../../windows/arrays-cpp-component-extensions.md).

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