---
title: Пример результатов вызова | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 5cc5d5f96b5ffabd5397f26b6ff1372232fe0cd6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32421423"
---
# <a name="results-of-calling-example"></a>Пример результатов вызова
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
  
## <a name="cdecl"></a>__cdecl  
 Упрощенное имя функции на языке C — _MyFunc.  
  
 ![Соглашение о вызовах CDECL](../cpp/media/vc37i01.gif "vc37I01")  
Соглашение о вызовах __cdecl  
  
## <a name="stdcall-and-thiscall"></a>__stdcall и thiscall  
 C внутреннего имени (`__stdcall`) — «_MyFunc@20.» Упрощенное имя на языке C++ является собственным.  
  
 ![&#95;&#95;STDCALL и соглашения о вызовах thiscall](../cpp/media/vc37i02.gif "vc37I02")  
Соглашения о вызовах __stdcall и thiscall  
  
## <a name="fastcall"></a>__fastcall  
 C внутреннего имени (`__fastcall`) — "@MyFunc@20.» Упрощенное имя на языке C++ является собственным.  
  
 ![Соглашение о вызовах &#95; &#95;fastcall](../cpp/media/vc37i03.gif "vc37I03")  
Соглашение о вызовах __fastcall  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Пример вызова. Прототип и вызов функции](../cpp/calling-example-function-prototype-and-call.md)