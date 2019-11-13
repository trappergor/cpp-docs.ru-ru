---
title: Предупреждение компилятора (уровень 1) C4674
ms.date: 11/04/2016
f1_keywords:
- C4674
helpviewer_keywords:
- C4674
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
ms.openlocfilehash: b9428a593ff59cbdfa6d8eb369413a560b4a5ad2
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052545"
---
# <a name="compiler-warning-level-1-c4674"></a>Предупреждение компилятора (уровень 1) C4674

"метод": требуется объявление как "static" и наличие строго одного параметра

Неправильная сигнатура оператора преобразования. Метод не считается пользовательским преобразованием. Дополнительные сведения об определении операторов см. в разделе пользовательские [операторы (C++/CLI)](../../dotnet/user-defined-operators-cpp-cli.md) и пользовательские [преобразования (C++/CLI)](../../dotnet/user-defined-conversions-cpp-cli.md).

## <a name="example"></a>Пример

При компиляции следующего примера будет выдано предупреждение C4674.

```cpp
// C4674.cpp
// compile with: /clr /WX /W1 /LD
ref class G {
   int op_Implicit(int i) {   // C4674
      return 0;
   }
};
```
