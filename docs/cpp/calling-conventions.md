---
title: Соглашения о вызовах
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions
ms.assetid: 11b1e45c-8fd1-420b-bca0-a19e294c1d85
ms.openlocfilehash: 432cb1b6910db5ea735288edfbf6aa9e10f0a486
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190291"
---
# <a name="calling-conventions"></a>Соглашения о вызовах

В компиляторе Visual C/C++ принято несколько разных соглашений о вызовах внутренних и внешних функций. Зная эти подходы, вам будет проще выполнять отладку программ и привязывать свой код к процедурам на языке ассемблера.

В разделах, посвященных этой теме, говорится о том, чем различаются эти соглашения о вызовах, как передаются аргументы и как функции возвращают значения. Кроме того, в них рассматриваются вызовы возможностей с атрибутом naked — дополнительная возможность, благодаря которой вы сможете создавать собственный код пролога и эпилог.

Сведения о соглашениях о вызовах для процессоров x64 см. в разделе [соглашение о вызовах](../build/x64-calling-convention.md).

## <a name="topics-in-this-section"></a>Разделы этой статьи

- [Правила передачи аргументов и именования](../cpp/argument-passing-and-naming-conventions.md) (`__cdecl`, `__stdcall`, `__fastcall`и др.)

- [Пример вызова. Прототип и вызов функции](../cpp/calling-example-function-prototype-and-call.md)

- [Использование вызовов функций с атрибутом naked для записи пользовательского кода пролога или эпилога](../cpp/naked-function-calls.md)

- [Сопроцессор для вычислений с плавающей запятой и соглашения о вызовах](../cpp/floating-point-coprocessor-and-calling-conventions.md)

- [Устаревшие соглашения о вызовах](../cpp/obsolete-calling-conventions.md)

## <a name="see-also"></a>См. также раздел

[Модификаторы, используемые в системах Майкрософт](../cpp/microsoft-specific-modifiers.md)
