---
title: Соглашения о вызовах | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- calling conventions
ms.assetid: 11b1e45c-8fd1-420b-bca0-a19e294c1d85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e9e65dfd7f7cff25debd8eb0d00a7e3bb0397692
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32410896"
---
# <a name="calling-conventions"></a>Соглашения о вызовах
В компиляторе Visual C/C++ принято несколько разных соглашений о вызовах внутренних и внешних функций. Зная эти подходы, вам будет проще выполнять отладку программ и привязывать свой код к процедурам на языке ассемблера.  
  
 В разделах, посвященных этой теме, говорится о том, чем различаются эти соглашения о вызовах, как передаются аргументы и как функции возвращают значения. Кроме того, в них рассматриваются вызовы возможностей с атрибутом naked — дополнительная возможность, благодаря которой вы сможете создавать собственный код пролога и эпилог.  
  
 Сведения о соглашения о вызовах для x64 процессоров, в разделе [соглашение о вызовах](../build/calling-convention.md).  
  
## <a name="topics-in-this-section"></a>Подразделы в этом разделе  
  
-   [Передача аргументов и соглашения об именовании](../cpp/argument-passing-and-naming-conventions.md) (`__cdecl`, `__stdcall`, `__fastcall`, а другие —)  
  
-   [Пример вызова. Прототип и вызов функции](../cpp/calling-example-function-prototype-and-call.md)  
  
-   [Использование вызовы функций naked для написания кода пролога и эпилога](../cpp/naked-function-calls.md)  
  
-   [Сопроцессор для вычислений с плавающей запятой и соглашения о вызовах](../cpp/floating-point-coprocessor-and-calling-conventions.md)  
  
-   [Устаревшие соглашения о вызовах](../cpp/obsolete-calling-conventions.md)  
  
## <a name="see-also"></a>См. также  
 [Модификаторы, используемые в системах Майкрософт](../cpp/microsoft-specific-modifiers.md)