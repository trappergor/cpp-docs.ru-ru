---
title: Грамматика препроцессора
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
ms.openlocfilehash: f0916e3cc9bbdb398db693286dacc4517df03557
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222258"
---
# <a name="preprocessor-grammar"></a>Грамматика препроцессора

*Строка управления*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#define** *идентификатор* *Строка токена* <sub>неявное согласие</sub>\
&nbsp;&nbsp;&nbsp;&nbsp; **#define** *идентификатор* **(** &#x2800;идентификатор&#x200B;<sub>OPT</sub> **,** ... **,** *идентификатор* &#x200B; <sub></sub>opt&#x2800; **)** *токен — строка*<sub></sub>\
&nbsp;&nbsp;&nbsp;&nbsp; **#include** **"** _путь — спецификация_ **"** \
&nbsp;&nbsp;&nbsp;&nbsp; **#include** _путь — спецификация_ **\<** **>** \
&nbsp;&nbsp;&nbsp;&nbsp; **#line** *последовательность цифр* **"** _имя файла_ **"** &#x200B; <sub>неявное согласие</sub>  \
&nbsp;&nbsp;&nbsp;&nbsp; **#undef** *идентификатор*\
&nbsp;&nbsp;&nbsp;&nbsp; **#error** *Строка токена*\
&nbsp;&nbsp;&nbsp;&nbsp; **#pragma** *Строка токена*

*константное выражение*: \
&nbsp;&nbsp;&nbsp;&nbsp;**определено (** &#x2800;*идентификатор*&#x2800; **)** \
&nbsp;&nbsp;&nbsp;&nbsp;**определен** *идентификатор*\
&nbsp;&nbsp;&nbsp;&nbsp;любое другое константное выражение

*условное*: \
&nbsp;&nbsp;&nbsp;&nbsp;*Если-часть* *elif — части* <sub>неявное согласие</sub> *else-Part* <sub>неявное согласие</sub> *endif-строка*

*If-Part*: \
&nbsp;&nbsp;&nbsp;&nbsp;*Если-Line* *текстовая надпись*

*If-Line*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#if** *константное выражение*\
&nbsp;&nbsp;&nbsp;&nbsp; **#ifdef** *идентификатор*\
&nbsp;&nbsp;&nbsp;&nbsp; **#ifndef** *идентификатор*

*elif — части*: \
&nbsp;&nbsp;&nbsp;&nbsp;*elif — строка* *текстовая надпись*\
&nbsp;&nbsp;&nbsp;&nbsp;*elif — части* *elif — строка* *текстовая надпись*

*elif-строка*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#elif** *константное выражение*

*else-Part*: \
&nbsp;&nbsp;&nbsp;&nbsp;*else-Line* *текстовая надпись*

*else-Line*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#else**

*endif-строка*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#endif**

*последовательность цифр*: \
&nbsp;&nbsp;&nbsp;&nbsp;*число*\
&nbsp;&nbsp;&nbsp;&nbsp;*digit-sequence* *digit*

*digit*: один из \
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**

*Строка токена*: \
&nbsp;&nbsp;&nbsp;&nbsp;Строка токенов

*токен*: \
&nbsp;&nbsp;&nbsp;&nbsp;*This*\
&nbsp;&nbsp;&nbsp;&nbsp;*Идентификатор*\
&nbsp;&nbsp;&nbsp;&nbsp;*выходит*\
&nbsp;&nbsp;&nbsp;&nbsp;*станции*\
&nbsp;&nbsp;&nbsp;&nbsp;*punctuator*

*имя файла*: \
&nbsp;&nbsp;&nbsp;&nbsp;Имя файла допустимой операционной системы

*path-Spec*: \
&nbsp;&nbsp;&nbsp;&nbsp;Допустимый путь к файлу

*текст*: \
&nbsp;&nbsp;&nbsp;&nbsp;Любая последовательность текста

> [!NOTE]
> Следующие Нетерминальные значения расширены в разделе [лексические обозначения](../cpp/lexical-conventions.md) справочника *C++* по языку: константа, *константное выражение*, *идентификатор*, *ключевое слово*, *оператор*и  *знак препинания*.

## <a name="see-also"></a>См. также

[Сводка по грамматике (C++C/)](../preprocessor/grammar-summary-c-cpp.md)
