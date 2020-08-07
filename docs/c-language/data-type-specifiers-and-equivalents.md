---
title: Спецификаторы и эквиваленты типов данных
ms.date: 11/04/2016
helpviewer_keywords:
- type specifiers [C++], list
- widening integers
- data types [C++], equivalents
- sign-extending integral types
- zero-extending
- identifiers, data type
- data types [C++], specifiers
- simple types, names
- type names [C++], simple
ms.assetid: 0d4b515a-4f68-4786-83cf-a5d43c7cb6f3
ms.openlocfilehash: cc8ba746bea7f6ea885beb625de414d83367b53f
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520685"
---
# <a name="data-type-specifiers-and-equivalents"></a>Спецификаторы и эквиваленты типов данных

В этой книге в большинстве случаев вместо полных форм описателей типов используются формы, приведенные в следующей таблице. При этом предполагается, что тип **`char`** является знаковым по умолчанию. Таким образом, если в этой книге указывается тип **`char`** , то это означает то же, что и **`signed char`** .

## <a name="type-specifiers-and-equivalents"></a>Спецификаторы типов и их эквиваленты

| Спецификаторы типов | Эквиваленты |
|--|--|
| **`signed char`** <sup>1</sup> | **`char`** |
| **`signed int`** | **`signed`** , **`int`** |
| **`signed short int`** | **`short`** , **`signed short`** |
| **`signed long int`** | **`long`** , **`signed long`** |
| **`unsigned char`** | — |
| **`unsigned int`** | **`unsigned`** |
| **`unsigned short int`** | **`unsigned short`** |
| **`unsigned long int`** | **`unsigned long`** |
| **`float`** | — |
| **`long double`** <sup>2</sup> | — |

<sup>1</sup> Если вы указали, что тип **`char`** по умолчанию является беззнаковым (указав параметр компилятора **`/J`** ), вы не сможете сократить **`signed char`** до **`char`** .

<sup>2</sup> В 32- и 64-разрядных операционных системах компилятор Microsoft С устанавливает соответствие между типами **`long double`** и **`double`** .

**Блок, относящийся только к системам Microsoft**

При помощи параметра компилятора **`/J`** можно указать, что тип **`char`** по умолчанию является не **`signed char`** , а **`unsigned char`** . При использовании этого параметра описатель **`char`** означает то же, что и **`unsigned char`** . Для объявления знакового символьного значения необходимо использовать ключевое слово **`signed`** . Если значение **`char`** явным образом объявлено как **`signed`** , то параметр **`/J`** на него не влияет, и его расширение до типа **`int`** выполняется с расширением знака. Расширение типа **`char`** до типа **`int`** выполняется с дополнением нулями.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Спецификаторы типов C](../c-language/c-type-specifiers.md)
