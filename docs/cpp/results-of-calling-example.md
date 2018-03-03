---
title: "Пример результатов вызова | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eaa47af17e46f51ef92cc15b8d2275b2ed8e05f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="results-of-calling-example"></a>Пример результатов вызова
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
  
## <a name="cdecl"></a>__cdecl  
 Упрощенное имя функции на языке C — _MyFunc.  
  
 ![Соглашение о вызовах CDECL](../cpp/media/vc37i01.gif "vc37I01")  
Соглашение о вызовах __cdecl  
  
## <a name="stdcall-and-thiscall"></a>__stdcall и thiscall  
 C внутреннего имени (`__stdcall`) — «_MyFunc@20.» Упрощенное имя на языке C++ является собственным.  
  
 ![&#95; &#95; stdcall и соглашения о вызовах thiscall](../cpp/media/vc37i02.gif "vc37I02")  
Соглашения о вызовах __stdcall и thiscall  
  
## <a name="fastcall"></a>__fastcall  
 C внутреннего имени (`__fastcall`) — "@MyFunc@20.» Упрощенное имя на языке C++ является собственным.  
  
 ![Соглашение о вызовах для &#95; &#95; fastcall](../cpp/media/vc37i03.gif "vc37I03")  
Соглашение о вызовах __fastcall  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Пример вызова. Прототип и вызов функции](../cpp/calling-example-function-prototype-and-call.md)