---
title: Пример результатов вызова
ms.date: 11/19/2018
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
ms.openlocfilehash: dcd1f9002362b7726883c6ce4f74fda9ab593544
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175422"
---
# <a name="results-of-calling-example"></a>Пример результатов вызова

**Блок, относящийся только к системам Microsoft**

## <a name="cdecl"></a>__cdecl

— Имя функции на языке C `_MyFunc`.

![Соглашение о вызовах CDECL](../cpp/media/vc37i01.gif "соглашение о вызовах CDECL") <br/>
**__Cdecl** соглашение о вызовах

## <a name="stdcall-and-thiscall"></a>__stdcall и thiscall

C внутреннее имя (**__stdcall**) является `_MyFunc@20`. Имя C++ декорированные зависит от реализации.

![&#95;&#95;STDCALL и соглашения о вызовах thiscall](../cpp/media/vc37i02.gif "&#95;&#95;stdcall и соглашения о вызовах thiscall") <br/>
Соглашения о вызовах __stdcall и thiscall

## <a name="fastcall"></a>__fastcall

C внутреннее имя (**__fastcall**) является `@MyFunc@20`. Имя C++ декорированные зависит от реализации.

![Соглашение о вызовах для &#95; &#95;fastcall](../cpp/media/vc37i03.gif "соглашение о вызовах для &#95; &#95;fastcall") <br/>
Соглашение о вызовах __fastcall

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Пример вызова. Прототип и вызов функции](../cpp/calling-example-function-prototype-and-call.md)