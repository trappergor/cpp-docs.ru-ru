---
title: Ошибка компилятора C3370
ms.date: 11/04/2016
f1_keywords:
- C3370
helpviewer_keywords:
- C3370
ms.assetid: ee6d4c85-78fc-42b2-836e-5cc491a3b2ba
ms.openlocfilehash: 4200cb7840899ad7b3719e949138010bd478ea3f
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503178"
---
# <a name="compiler-error-c3370"></a>Ошибка компилятора C3370

"имя_модуля_idl": idl_module еще не определен

Прежде чем использовать [idl_module](../../windows/attributes/idl-module.md) для указания точки входа в DLL, вы должны сначала с помощью `idl_module` указать имя библиотеки DLL.

В следующем примере возникает ошибка C3370:

```cpp
// C3370.cpp
[module(name=MyLibrary)];
// uncomment the following line to resolve the error
// [idl_module(name="name1", dllname=x.dll)];
[idl_module(name="name1"), entry(100)] // C3370
int f1();

int main()
{
}
```
