---
title: Пример результатов вызова | Документация Майкрософт
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5687adfada8657ae26edd9001db8990ff08864e9
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894700"
---
# <a name="results-of-calling-example"></a>Пример результатов вызова

**Блок, относящийся только к системам Microsoft**

## <a name="cdecl"></a>__cdecl
— Имя функции на языке C `_MyFunc`.

![Соглашение о вызовах CDECL](../cpp/media/vc37i01.gif "vc37I01")  
**__Cdecl** соглашение о вызовах

## <a name="stdcall-and-thiscall"></a>__stdcall и thiscall

C внутреннее имя (**__stdcall**) является `_MyFunc@20`. Имя C++ декорированные зависит от реализации.

![&#95;&#95;STDCALL и соглашения о вызовах thiscall](../cpp/media/vc37i02.gif "vc37I02")  
Соглашения о вызовах __stdcall и thiscall

## <a name="fastcall"></a>__fastcall

C внутреннее имя (**__fastcall**) является `@MyFunc@20`. Имя C++ декорированные зависит от реализации.

![Соглашение о вызовах для &#95; &#95;fastcall](../cpp/media/vc37i03.gif "vc37I03")  
Соглашение о вызовах __fastcall

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Пример вызова. Прототип и вызов функции](../cpp/calling-example-function-prototype-and-call.md)