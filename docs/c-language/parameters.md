---
title: Параметры | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arguments [C++], function
- function parameters
- parameters [C++]
- function arguments, vs. parameters
- parameters [C++], function
- functions [C], parameters
- function parameters, syntax
- ellipses (...), parameters
- '... ellipsis'
ms.assetid: 8f2b8026-78b5-4e21-86a3-bf0f91f05689
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d93dfd518499f4f34813a7fa6aae35da0e8175b
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766104"
---
# <a name="parameters"></a>Параметры

Аргументы — это имена значений, переданных в функцию в результате вызова функции. Параметры — это значения, которые ожидает получить функция. В прототипе функции в круглых скобках после имени функции содержится полный список параметров функции и их типов. Объявления параметров определяют типы, размеры и идентификаторы значений, хранящихся в параметрах.

## <a name="syntax"></a>Синтаксис

*function-definition*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers*<sub>opt</sub> *attribute-seq*<sub>opt</sub> *declarator* *declaration-list*<sub>opt</sub> *compound-statement*

/\* *attribute-seq* Поддерживается только компилятором Microsoft \*/

*declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*pointer*<sub>opt</sub> *direct-declarator*

*direct-declarator*: /\* Декларатор функции \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*direct-declarator*  **(**  *parameter-type-list*  **)** /\* Декларатор нового стиля \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*direct-declarator*  **(**  *identifier-list*<sub>opt</sub> **)** /\* Декларатор устаревшего стиля \*/

*parameter-type-list*: /\* Список параметров \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-list* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-list* **, ...**

*parameter-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-list* **,**  *parameter-declaration*

*parameter-declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers* *declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers* *abstract-declarator*<sub>opt</sub>

Параметр *parameter-type-list* содержит последовательность объявлений параметров, разделенных запятыми. Форма каждого параметра в списке параметров выглядит следующим образом.

```C
[register]  type-specifier [declarator]
```

Параметры функции, объявленные с атрибутом **auto**, создают ошибки. Идентификаторы параметров используются в теле функции для ссылки на значения, переданные в функцию. Параметрам можно присвоить имена в прототипе, но имена выходят за пределы области в конце объявления. Поэтому имена параметров можно присвоить таким же образом или по-другому в определении функции. Эти идентификаторы невозможно переопределить в крайнем блоке тела функции, но их можно переопределить во внутренних вложенных блоках, как если бы список параметров был внешним блоком.

Каждому идентификатору в *parameter-type-list* должен предшествовать соответствующий описатель типа, как показано в следующем примере.

```C
void new( double x, double y, double z )
{
    /* Function body here */
}
```

Если в списке имеется хотя бы один параметр, то список может заканчиваться запятой и тремя точками (**, ...**). Эта конструкция, называемая нотацией с многоточием, указывает переменное число аргументов функции. (Дополнительные сведения см. в статье [Вызовы с переменным количеством аргументов](../c-language/calls-with-a-variable-number-of-arguments.md).) Однако в вызове функции должно быть как минимум столько аргументов, сколько параметров имеется перед последней запятой.

Если аргументы не требуется передавать в функцию, список параметров заменяется ключевым словом `void`. В данном случае использование ключевого слова `void` отличается от его использования в качестве описателя типа.

Порядок и тип параметров, включая любое использование нотации с многоточием, должны быть одинаковыми во всех объявлениях функций (если есть) и в определении функции. Типы аргументов после обычных арифметических преобразований должны быть совместимы по назначению с типами соответствующих параметров. (Дополнительные сведения об арифметических преобразованиях см. в статье [Обычные арифметические преобразования](../c-language/usual-arithmetic-conversions.md).) Аргументы после многоточия не проверяются. Параметр может иметь любой основной тип, тип структуры, объединения, указателя или массива.

Компилятор выполняет обычные арифметические преобразования отдельно для каждого параметра и для каждого аргумента при необходимости. После преобразования параметры имеют длину не менее `int` и никогда не имеют типа **float**, если для конкретного параметра в прототипе явно не задан тип **float**. Это означает, например, что объявление параметра как `char` будет иметь тот же эффект, что и его объявление как `int`.

## <a name="see-also"></a>См. также

[Определения функций в C](../c-language/c-function-definitions.md)