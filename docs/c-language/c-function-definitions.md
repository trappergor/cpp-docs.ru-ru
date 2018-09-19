---
title: Определения функций в C| Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function declarators
- function definitions
- declaring functions, about function declarations
- declaring functions, declarators
- functions [C], parameters
- declarators, functions
- function parameters, function definitions
- function body
- declaring functions, variables
ms.assetid: ebab23c8-6eb8-46f3-b21d-570cd8457a80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 265dfe599d4c3586b350787baab5977562326991
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757686"
---
# <a name="c-function-definitions"></a>Определения функций в C
Определение функции задает имя функции, типы и число ожидаемых параметров, а также тип значений, возвращаемый функцией. Определение функции также содержит тело функции с объявлениями ее локальных переменных и операторы, которые определяют действия, выполняемые функцией.

## <a name="syntax"></a>Синтаксис

*translation-unit*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*external-declaration* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*translation-unit* *external-declaration*

*external-declaration*: /\* Допускается только в области видимости файла (внешней) \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*function-definition*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration*

*function-definition*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers*<sub>opt</sub> *attribute-seq*<sub>opt</sub> *declarator* *declaration-list*<sub>opt</sub> *compound-statement*

/\* *attribute-seq* Поддерживается только компилятором Microsoft \*/

Параметры прототипа:

*declaration-specifiers*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*storage-class-specifier* *declaration-specifiers*<sub>opt</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-specifier* *declaration-specifiers*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-qualifier* *declaration-specifiers*<sub>opt</sub>

*declaration-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-list* *declaration*

*declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*pointer*<sub>opt</sub> *direct-declarator*

*direct-declarator*: /\* Декларатор функции \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*direct-declarator*  **(**  *parameter-type-list*  **)** /\* New-style declarator \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*direct-declarator*  **(**  *identifier-list*<sub>opt</sub> **)** /\* Декларатор устаревшего стиля \*/

Для списка параметров в определении используется следующий синтаксис:

*parameter-type-list*: /\* Список параметров \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-list* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-list* **, ...**

*parameter-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-list* **,**  *parameter-declaration*

*parameter-declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers* *declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers* *abstract-declarator*<sub>opt</sub>

В определении функции устаревшего стиле для списка параметров используется следующий синтаксис:

*identifier-list*: /\* Используется в определениях и объявлениях функций устаревшего стиля \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier-list* **,**  *identifier*

Синтаксис тела функции:

*compound-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{** *declaration-list*<sub>opt</sub> *statement-list*<sub>opt</sub> **}**

Изменять объявление функции могут только описатели класса хранения **extern** и **static**. Описатель **extern** означает, что на функцию можно ссылаться из других файлов, т. е. имя функции экспортируется в компоновщик. Описатель **static** означает, что на функцию невозможно ссылаться из других файлов. Имя такой функции не экспортируется компоновщиком. Если в определении функции класс хранения не указан, используется класс **extern**. В любом случае функция всегда видна от точки определения до конца файла.

Сочетание необязательных деклараторов *declaration-specifiers* и обязательного декларатора *declarator* определяет тип возвращаемого значения и имя функции. Декларатор *declarator* — это сочетание идентификатора, задающего имя функции, и круглых скобок после имени функции. Необязательный нетерминальный компонент *attribute-seq* используется только для систем Microsoft и описан в статье [Атрибуты функций](../c-language/function-attributes.md).

Декларатор *direct-declarator* (в синтаксисе *declarator*) указывает имя определяемой функции и идентификаторы ее параметров. Если *direct-declarator* содержит список *parameter-type-list*, в нем определяются типы всех параметров. Такой декларатор также является прототипом функции для ее последующих вызовов.

Элемент *declaration* в списке *declaration-list* в определении функции не может содержать других описателей *storage-class-specifier*, кроме **register**. Описатель *type-specifier* в синтаксисе *declaration-specifiers* можно опустить, только если для типа **int** указан класс хранения **register**.

*compound-statement* представляет собой тело функции, где размещаются объявления локальных переменных, ссылки на внешние объявленные элементы и операторы.

Компоненты определения функции подробно рассматриваются в статьях [Атрибуты функций](../c-language/function-attributes.md), [Класс хранения](../c-language/storage-class.md), [Тип возвращаемого значения](../c-language/return-type.md), [Параметры](../c-language/parameters.md) и [Текст функции](../c-language/function-body.md).

## <a name="see-also"></a>См. также
[Функции](../c-language/functions-c.md)