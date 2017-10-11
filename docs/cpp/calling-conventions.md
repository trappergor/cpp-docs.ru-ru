---
title: "Соглашения о вызовах | Документы Microsoft"
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
- calling conventions
ms.assetid: 11b1e45c-8fd1-420b-bca0-a19e294c1d85
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: bbdee0427dcefc019214e7f9af16831f162cef83
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

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
