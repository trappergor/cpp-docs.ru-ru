---
title: Ошибка компилятора C3641 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3641
dev_langs:
- C++
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99aef6bcfd8ac7ea89cb62fda37c7aec012e16de
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704949"
---
# <a name="compiler-error-c3641"></a>Ошибка компилятора C3641

> "*функция*": недопустимое соглашение о вызовах «соглашение_о_вызовах» для функции, скомпилированные с параметром/clr: pure или/CLR: safe

## <a name="remarks"></a>Примечания

**/CLR: pure** и **/CLR: safe** параметры компилятора являются устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017 г.

Только [__clrcall](../../cpp/clrcall.md) соглашение о вызовах может использоваться с [/CLR: pure](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3641:

```cpp
// C3641.cpp
// compile with: /clr:pure /c
void __cdecl f() {}   // C3641
```