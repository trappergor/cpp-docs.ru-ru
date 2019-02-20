---
title: Расширенные атрибуты классов хранения в C
ms.date: 11/04/2016
helpviewer_keywords:
- __declspec keyword [C]
- extended attributes
- extended storage-class attributes
- storage class specifiers, C storage classes
ms.assetid: 2580735c-f5bf-46ab-9468-0696893d82be
ms.openlocfilehash: 9b0c8b60dab3229d5d5c162f7bafc959fa2558f0
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56146961"
---
# <a name="c-extended-storage-class-attributes"></a>Расширенные атрибуты классов хранения в C

**Блок, относящийся только к системам Microsoft**

Более актуальные сведения по этой теме вы найдете в [описании __declspec](../cpp/declspec.md) в справочнике по языку C++.

Расширенный синтаксис атрибутов упрощает и стандартизирует расширения для систем Microsoft в соответствии с правилами языка C. К атрибутам класса хранения, в которых используется расширенный синтаксис атрибутов, относятся: thread, naked, dllimport и dllexport.

Расширенный синтаксис атрибутов для указания информации о классе памяти использует ключевое слово , которое указывает, что экземпляр заданного типа должен храниться с соответствующим атрибутом класса хранения для систем Microsoft (thread, naked, dllimport или dllexport). Имеются и другие модификаторы класса хранения: ключевые слова static и extern. Однако эти ключевые слова входят в стандарт ANSI C, и как таковые они не используются с расширенным синтаксисом атрибутов.

## <a name="syntax"></a>Синтаксис

*storage-class-specifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__declspec (** *extended-decl-modifier-seq* **)** /\* Поддерживается только компилятором Майкрософт \*/

*extended-decl-modifier-seq*:&nbsp;&nbsp;&nbsp;&nbsp;/\* только для Microsoft \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*extended-decl-modifier*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*extended-decl-modifier-seq* *extended-decl-modifier*

*extended-decl-modifier*:&nbsp;&nbsp;&nbsp;&nbsp;/\* только для Microsoft \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**thread**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**naked**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**

Модификаторы объявления разделяются пробелами. Обратите внимание, что *extended-decl-modifier-seq* может быть пустой, в этом случае ключевое слово __declspec игнорируется.

Атрибуты класса хранения thread, naked, dllimport и dllexport являются свойством только объявления данных или функции, к которому они применяются; они не переопределяют атрибуты типа самой функции. Атрибут thread влияет только на данные. Атрибут naked влияет только на функции. Атрибуты dllimport и dllexport влияют на функции и данные.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Объявления и типы](../c-language/declarations-and-types.md)
