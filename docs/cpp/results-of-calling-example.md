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
ms.openlocfilehash: 1bf5fe62b8ef2b7a37bf72b7a40e5d47af3f3961
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225882"
---
# <a name="results-of-calling-example"></a>Пример результатов вызова

**Блок, относящийся только к системам Microsoft**

## <a name="__cdecl"></a>__cdecl

Имя функции с декорированием в C — `_MyFunc` .

![Соглашение о вызовах CDECL](../cpp/media/vc37i01.gif "Соглашение о вызовах CDECL") <br/>
**`__cdecl`** Соглашение о вызовах

## <a name="__stdcall-and-thiscall"></a>__stdcall и thiscall

Декорированное имя C ( **`__stdcall`** ) имеет значение `_MyFunc@20` . Декорированное имя C++ зависит от конкретной реализации.

![Соглашения о вызовах&#95;&#95;STDCALL и thiscall](../cpp/media/vc37i02.gif "Соглашения о вызовах &#95;&#95;STDCALL и thiscall") <br/>
Соглашения о вызовах __stdcall и thiscall

## <a name="__fastcall"></a>__fastcall

Декорированное имя C ( **`__fastcall`** ) имеет значение `@MyFunc@20` . Декорированное имя C++ зависит от конкретной реализации.

![Соглашение о вызовах для &#95;&#95;fastcall](../cpp/media/vc37i03.gif "Соглашение о вызовах для &#95;&#95;fastcall") <br/>
Соглашение о вызовах __fastcall

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Пример вызова: прототип функции и вызов](../cpp/calling-example-function-prototype-and-call.md)
