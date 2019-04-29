---
title: Предупреждение компилятора (уровень 1) C4674
ms.date: 11/04/2016
f1_keywords:
- C4674
helpviewer_keywords:
- C4674
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
ms.openlocfilehash: f7db2f37224a8defffb545b0cfaf018fd4654227
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374551"
---
# <a name="compiler-warning-level-1-c4674"></a>Предупреждение компилятора (уровень 1) C4674

"метод": требуется объявление как "static" и наличие строго одного параметра

Неправильная сигнатура оператора преобразования. Метод не считается пользовательским преобразованием. Дополнительные сведения об определяющих операторах см. в разделе [определяемые пользователем операторы (C++выполняет)](../../dotnet/user-defined-operators-cpp-cli.md) и [заданных пользователем преобразований (C++выполняет)](../../dotnet/user-defined-conversions-cpp-cli.md).

## <a name="example"></a>Пример

При компиляции следующего примера будет выдано предупреждение C4674.

```
// C4674.cpp
// compile with: /clr /WX /W1 /LD
ref class G {
   int op_Implicit(int i) {   // C4674
      return 0;
   }
};
```
