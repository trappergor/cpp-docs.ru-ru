---
title: Практическое руководство. Определение выходного параметра
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- function parameters
- out parameters
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
ms.openlocfilehash: 8c3499a2916eda7ab96f7958df190c803206741e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437094"
---
# <a name="how-to-specify-an-out-parameter"></a>Практическое руководство. Определение выходного параметра

В этом примере показано, как указать, что параметр функции является выходным параметром и способ вызова этой функции из программы на C#.

Выходной параметр указывается в Visual C++ с использованием <xref:System.Runtime.InteropServices.OutAttribute> .

## <a name="example"></a>Пример

В первой части этого примера является DLL Visual C++ с типом, который содержит функцию с выходным параметром.

```
// cpp_out_param.cpp
// compile with: /LD /clr:safe
using namespace System;
public value struct TestStruct {
   static void Test([Runtime::InteropServices::Out] String^ %s) {
      s = "a string";
   }
};
```

## <a name="example"></a>Пример

Это клиент C#, который использует компонент Visual C++, созданных в предыдущем примере.

```
// cpp_out_param_2.cs
// compile with: /reference:cpp_out_param.dll
using System;
class TestClass {
   public static void Main() {
      String t;
      TestStruct.Test(out t);
      System.Console.WriteLine(t);
   }
}
```

```Output
a string
```

## <a name="see-also"></a>См. также

[Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)