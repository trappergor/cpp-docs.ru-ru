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
ms.openlocfilehash: edbeb187e568b833673d91ef70ff57fbd460659c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179059"
---
# <a name="results-of-calling-example"></a>Пример результатов вызова

**Блок, относящийся только к системам Microsoft**

## <a name="__cdecl"></a>__cdecl

Имя функции с декорированием языка C — `_MyFunc`.

![Соглашение о вызовах CDECL](../cpp/media/vc37i01.gif "Соглашение о вызовах CDECL") <br/>
Соглашение о вызовах **__cdecl**

## <a name="__stdcall-and-thiscall"></a>__stdcall и thiscall

Внутреннее имя C ( **__stdcall**) `_MyFunc@20`. C++ Декорированное имя зависит от реализации.

![&#95;&#95;соглашения о вызовах STDCALL и thiscall](../cpp/media/vc37i02.gif "&#95;&#95;соглашения о вызовах STDCALL и thiscall") <br/>
Соглашения о вызовах __stdcall и thiscall

## <a name="__fastcall"></a>__fastcall

Внутреннее имя C ( **__fastcall**) `@MyFunc@20`. C++ Декорированное имя зависит от реализации.

![Соглашение о вызовах для &#95; &#95;fastcall](../cpp/media/vc37i03.gif "Соглашение о вызовах для &#95; &#95;fastcall") <br/>
Соглашение о вызовах __fastcall

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Пример вызова. Прототип и вызов функции](../cpp/calling-example-function-prototype-and-call.md)
