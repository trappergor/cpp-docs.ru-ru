---
title: Пример результатов вызова
ms.date: 09/05/2018
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
ms.openlocfilehash: 96582e48912bb591d869bbc4df179299e6459f1e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500946"
---
# <a name="results-of-calling-example"></a>Пример результатов вызова

**Блок, относящийся только к системам Microsoft**

## <a name="cdecl"></a>__cdecl

— Имя функции на языке C `_MyFunc`.

![Соглашение о вызовах CDECL](../cpp/media/vc37i01.gif "vc37I01") **__cdecl** соглашение о вызовах

## <a name="stdcall-and-thiscall"></a>__stdcall и thiscall

C внутреннее имя (**__stdcall**) является `_MyFunc@20`. Имя C++ декорированные зависит от реализации.

![&#95;&#95;STDCALL и соглашения о вызовах thiscall](../cpp/media/vc37i02.gif "vc37I02") __stdcall и thiscall, соглашения о вызовах

## <a name="fastcall"></a>__fastcall

C внутреннее имя (**__fastcall**) является `@MyFunc@20`. Имя C++ декорированные зависит от реализации.

![Соглашение о вызовах для &#95; &#95;fastcall](../cpp/media/vc37i03.gif "vc37I03") соглашение о вызовах __fastcall

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Пример вызова. Прототип и вызов функции](../cpp/calling-example-function-prototype-and-call.md)