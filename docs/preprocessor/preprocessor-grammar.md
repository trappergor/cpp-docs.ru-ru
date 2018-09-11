---
title: Грамматика препроцессора | Документация Майкрософт
ms.custom: ''
ms.date: 09/04/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56df4d0bfdaf87ace87a9f9dcbde85166929e642
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766120"
---
# <a name="preprocessor-grammar"></a>Грамматика препроцессора

*строки элемента управления*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#define** *идентификатор* *строке токена*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#define** <em>идентификатор</em>**(** *идентификатор*<sub>opt</sub> **,** ... **,** *идентификатор*<sub>opt</sub> **)** *строке токена*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#include** **"** *path-spec* **"**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#include** **\<** *path-spec* **>**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#line** *последовательность цифр***"** *filename* **"**<sub>opt  </sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#undef** *идентификатор*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#error** *строке токена*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#pragma** *строке токена*

*constant-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**определенные (** *идентификатор* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**определенные** *идентификатор*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Константное выражение

*условный* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*IF часть* *elif части*<sub>opt</sub> *else часть*<sub>opt</sub> *endif строка*

*IF часть* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*строки IF* *текста*

*строки IF* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#if** *константного выражения*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifdef** *идентификатор*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifndef** *идентификатор*

*elif части* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif строка* *текста*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif части* *elif строка* *текста*

*elif строка* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#elif** *константного выражения*

*Else часть* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Else строка* *текста*

*Else строка* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#else**

*ENDIF строка* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#endif**

*последовательность цифр* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*цифра*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*последовательность цифр* *цифра*

*цифра* : один из<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**

*токен строки* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Строка токенов

*токен* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Ключевое слово*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Идентификатор*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Константы*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Оператор*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*знак препинания*

*Имя файла* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Имя файла юридические операционной системы

*PATH-spec* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Допустимый путь к файлу

*текст* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Любая текстовая последовательность

> [!NOTE]
> Следующие Нетерминальные элементы в [лексические соглашения](../cpp/lexical-conventions.md) раздел *Справочник по языку C++*: *константы*, *константного выражения* , *идентификатор*, *ключевое слово*, *оператор*, и *знак препинания*.

## <a name="see-also"></a>См. также

[Общие сведения о грамматике (C/C++)](../preprocessor/grammar-summary-c-cpp.md)