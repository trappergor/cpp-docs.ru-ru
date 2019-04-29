---
title: Предупреждение компилятора C4956
ms.date: 11/04/2016
f1_keywords:
- C4956
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
ms.openlocfilehash: c15de8b22f56a2555cc763a45153139b1df01a31
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280846"
---
# <a name="compiler-warning-c4956"></a>Предупреждение компилятора C4956

> "*тип*": этот тип недоступен

## <a name="remarks"></a>Примечания

Это предупреждение создается, если указано [/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) , но код содержит тип, не подлежащий проверке. **/CLR: safe** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017.

Дополнительные сведения см. в разделе [чистый и проверяемый код (C++выполняет)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

Это предупреждение выдается в качестве ошибки, и его можно отключить с помощью прагмы [warning](../../preprocessor/warning.md) или параметра компилятора [/wd](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Пример

В следующем примере возникает ошибка C4956.

```cpp
// C4956.cpp
// compile with: /clr:safe
int* p;   // C4956
```