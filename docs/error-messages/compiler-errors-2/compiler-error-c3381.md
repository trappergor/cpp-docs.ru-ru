---
title: Ошибка компилятора C3381
ms.date: 11/04/2016
f1_keywords:
- C3381
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
ms.openlocfilehash: eadc9b45b4cd4f2d9b533f387dadd66be8acc963
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749572"
---
# <a name="compiler-error-c3381"></a>Ошибка компилятора C3381

"Assembly": Спецификаторы доступа сборки доступны только в коде, скомпилированном с параметром/CLR

Собственные типы могут быть видимыми за пределами сборки, но в компиляции **/CLR** можно указать только доступ к сборке для собственных типов.

Дополнительные сведения см. в разделе [видимость типов](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) и [/CLR (компиляция общеязыковой среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3381.

```cpp
// C3381.cpp
// compile with: /c
public class A {};   // C3381
```
