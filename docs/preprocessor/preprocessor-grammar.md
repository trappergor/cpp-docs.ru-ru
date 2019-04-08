---
title: Грамматика препроцессора
ms.date: 09/04/2018
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
ms.openlocfilehash: 6177cf5fddba549e410842ef3f270edcc13d4782
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032418"
---
# <a name="preprocessor-grammar"></a>Грамматика препроцессора

*строки элемента управления*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#define** *идентификатор* *строке токена*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#define** <em>идентификатор</em>**(** *идентификатор*<sub>opt</sub> **,** ... **,** *идентификатор*<sub>opt</sub> **)** *строке токена*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#include** **"** *path-spec* **"**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#include** **\<** *path-spec* **>**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#line** *последовательность цифр***"** *filename* **"**<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#undef** *identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#error** *строке токена*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#pragma** *строке токена*

*constant-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**определенные (** *идентификатор* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**определенные** *идентификатор*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Константное выражение

*условный* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*IF часть* *elif части*<sub>opt</sub> *else часть*<sub>opt</sub> *endif строка*

*IF часть* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*if-line* *text*

*строки IF* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#if** *constant-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifdef** *идентификатор*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifndef** *identifier*

*elif части* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif строка* *текста*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif части* *elif строка* *текста*

*elif строка* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#elif** *constant-expression*

*Else часть* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*else-line* *text*

*Else строка* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#else**

*ENDIF строка* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#endif**

*последовательность цифр* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*digit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*digit-sequence* *digit*

*цифра* : один из<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**

*токен строки* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Строка токенов

*токен* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*keyword*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*constant*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*operator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*punctuator*

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