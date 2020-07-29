---
title: Ошибка компилятора C3389
ms.date: 11/04/2016
f1_keywords:
- C3389
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
ms.openlocfilehash: 823b28deae3e3cfc18cdad8d37007bf8e8cff494
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221059"
---
# <a name="compiler-error-c3389"></a>Ошибка компилятора C3389

> __declspec (*ключевое слово*) нельзя использовать с параметрами/clr: pure или/CLR: Сейф

## <a name="remarks"></a>Remarks

Параметры компилятора **/clr: pure** и **/clr: Сейф** являются устаревшими в Visual Studio 2015 и не поддерживаются в Visual Studio 2017.

Используемый модификатор [__declspec](../../cpp/declspec.md) подразумевает состояние каждого процесса.  [параметр/clr: pure](../../build/reference/clr-common-language-runtime-compilation.md) подразумевает состояние каждого [домена приложения](../../cpp/appdomain.md) .  Таким образом, объявление переменной с `keyword` **`__declspec`** модификатором и компиляция с **параметром/clr: pure** не допускается.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3389:

```cpp
// C3389.cpp
// compile with: /clr:pure /c
__declspec(dllexport) int g2 = 0;   // C3389
```
