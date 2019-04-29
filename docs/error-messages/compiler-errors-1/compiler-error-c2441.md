---
title: Ошибка компилятора C2441
ms.date: 11/04/2016
f1_keywords:
- C2441
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
ms.openlocfilehash: 7fcf333f62253eb676c0f0ada1c927ab962ae1ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338926"
---
# <a name="compiler-error-c2441"></a>Ошибка компилятора C2441

> "*переменной*": символ, объявленный с параметром __declspec(process), должен быть константой в/CLR: pure режим

## <a name="remarks"></a>Примечания

**/CLR: pure** и **/CLR: safe** параметры компилятора признаны устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017.

По умолчанию, переменные находятся в каждом домене приложения, в разделе **/CLR: pure**. Переменная, помеченная как `__declspec(process)` под **/CLR: pure** может привести к ошибкам, если изменения в одном домене приложения и чтения в другом.

Таким образом, компилятор применяет правило каждого процесса, переменные быть `const` под **/CLR: pure**, что делает их чтения только во всех доменах приложения.

Дополнительные сведения см. в разделе [процесс](../../cpp/process.md) и [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2441.

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```