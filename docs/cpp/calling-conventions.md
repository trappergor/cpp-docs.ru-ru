---
title: Соглашения о вызовах
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions
ms.assetid: 11b1e45c-8fd1-420b-bca0-a19e294c1d85
ms.openlocfilehash: d351ae064b8c9bdd0599a1d6981166371a62af58
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216613"
---
# <a name="calling-conventions"></a>Соглашения о вызовах

В компиляторе Visual C/C++ принято несколько разных соглашений о вызовах внутренних и внешних функций. Зная эти подходы, вам будет проще выполнять отладку программ и привязывать свой код к процедурам на языке ассемблера.

В разделах, посвященных этой теме, говорится о том, чем различаются эти соглашения о вызовах, как передаются аргументы и как функции возвращают значения. Кроме того, в них рассматриваются вызовы возможностей с атрибутом naked — дополнительная возможность, благодаря которой вы сможете создавать собственный код пролога и эпилог.

Сведения о соглашениях о вызовах для процессоров x64 см. в разделе [соглашение о вызовах](../build/x64-calling-convention.md).

## <a name="topics-in-this-section"></a>Разделы этой статьи

- [Передача аргументов и соглашения об именовании](../cpp/argument-passing-and-naming-conventions.md) ( **`__cdecl`** ,, **`__stdcall`** **`__fastcall`** и др.)

- [Пример вызова: прототип функции и вызов](../cpp/calling-example-function-prototype-and-call.md)

- [Использование вызова функции с атрибутом naked для написания собственного кода пролога и эпилога](../cpp/naked-function-calls.md)

- [Соглашения о сопроцессоре и вызовах с плавающей точкой](../cpp/floating-point-coprocessor-and-calling-conventions.md)

- [Устаревшие соглашения о вызовах](../cpp/obsolete-calling-conventions.md)

## <a name="see-also"></a>См. также раздел

[Модификаторы, специфичные для Майкрософт](../cpp/microsoft-specific-modifiers.md)
