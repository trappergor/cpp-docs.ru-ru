---
title: Предупреждение компилятора C4936 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4936
dev_langs:
- C++
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0be4a565dd251da77174c401c23b8ed8bfc531b0
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34703943"
---
# <a name="compiler-warning-c4936"></a>Предупреждение компилятора C4936

> Данный __declspec поддерживается только при компиляции с параметрами /clr или /clr:pure

## <a name="remarks"></a>Примечания

**/CLR: pure** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017 г.

Использовался модификатор `__declspec` , но модификатор `__declspec` допустим только при компиляции с одним из параметров [/clr](../../build/reference/clr-common-language-runtime-compilation.md) .

Дополнительные сведения см. в разделах [appdomain](../../cpp/appdomain.md) и [process](../../cpp/process.md).

C4936 всегда выдается как ошибка.  Вы можете отключить C4936 с помощью директивы [warning](../../preprocessor/warning.md) .

## <a name="example"></a>Пример

При компиляции следующего примера возникнет ошибка C4936:

```cpp
// C4936.cpp
// compile with: /c
// #pragma warning (disable : 4936)
__declspec(process) int i;   // C4936
__declspec(appdomain) int j;   // C4936
```