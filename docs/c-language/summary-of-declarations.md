---
title: Общие сведения об объявлениях
ms.date: 11/04/2016
ms.assetid: 53a5e9e5-1a33-40b5-9dea-7f669b479329
ms.openlocfilehash: 894ed5e39ac8019048b6730d5e3b34de22f3a0c7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220851"
---
# <a name="summary-of-declarations"></a>Общие сведения об объявлениях

*`declaration`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`declaration-specifiers`* *`attribute-seq`* <sub>необ.</sub> *`init-declarator-list`* <sub>необ.</sub> **`;`**

*`declaration-specifiers`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`storage-class-specifier`* *`declaration-specifiers`* <sub>необ.</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`type-specifier`* *`declaration-specifiers`* <sub>необ.</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`type-qualifier`* *`declaration-specifiers`* <sub>необ.</sub>

*`attribute-seq`* :&nbsp;&nbsp;&nbsp;&nbsp;/\* Только для систем Майкрософт \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`attribute`* *`attribute-seq`* <sub>необ.</sub>

*`attribute`* : один из&nbsp;&nbsp;&nbsp;&nbsp;/\* Только для систем Майкрософт \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;[`__asm`](../assembler/inline/asm.md) [`__clrcall`](../cpp/clrcall.md) [`__stdcall`](../cpp/stdcall.md) [`__based`](../cpp/based-grammar.md) [`__fastcall`](../cpp/fastcall.md) [`__thiscall`](../cpp/thiscall.md) [`__cdecl`](../cpp/cdecl.md) [`__inline`](../cpp/inline-functions-cpp.md) [`__vectorcall`](../cpp/vectorcall.md)

*`init-declarator-list`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`init-declarator`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`init-declarator-list`*  **`,`**  *`init-declarator`*

*`init-declarator`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`declarator`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`declarator`*  **`=`**  *`initializer`*  /\* Для инициализации скалярных типов \*/

*`storage-class-specifier`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`auto`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`register`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`static`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`extern`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`typedef`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`__declspec (`** *`extended-decl-modifier-seq`* **`)`**  /\* Только для систем Майкрософт \*/

*`type-specifier`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`void`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`char`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`short`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`int`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`__int8`**  /\* Только для систем Майкрософт \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`__int16`**  /\* Только для систем Майкрософт \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`__int32`**  /\* Только для систем Майкрософт \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`__int64`**  /\* Только для систем Майкрософт \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`long`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`float`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`double`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`signed`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`unsigned`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`struct-or-union-specifier`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`enum-specifier`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`typedef-name`*

*`type-qualifier`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`const`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`volatile`**

*`declarator`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`pointer`* <sub>необ.</sub> *`direct-declarator`*

*`direct-declarator`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`identifier`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`(`** *`declarator`* **`)`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`direct-declarator`* **`[`** *`constant-expression`* <sub>необ.</sub> **`]`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`direct-declarator`* **`(`** *`parameter-type-list`* **`)`**  /\* Оператор объявления нового стиля \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`direct-declarator`* **`(`** *`identifier-list`* <sub>необ.</sub> **`)`**  /\* Оператор объявления старого стиля \*/

*`pointer`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>`*`</strong> *`type-qualifier-list`* <sub>необ.</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>`*`</strong> *`type-qualifier-list`* <sub>необ.</sub> *`pointer`*

*`parameter-type-list`* :&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/\* Список параметров \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`parameter-list`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`parameter-list`* **`, ...`**

*`parameter-list`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`parameter-declaration`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`parameter-list`* **`,`** *`parameter-declaration`*

*`type-qualifier-list`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`type-qualifier`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`type-qualifier-list`* *`type-qualifier`*

*`enum-specifier`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`enum`** *`identifier`* <sub>необ.</sub> **`{`** *`enumerator-list`* **`}`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`enum`** *`identifier`*

*`enumerator-list`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`enumerator`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`enumerator-list`* **`,`** *`enumerator`*

*`enumerator`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`enumeration-constant`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`enumeration-constant`* **`=`** *`constant-expression`*

*`enumeration-constant`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`identifier`*

*`struct-or-union-specifier`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`struct-or-union`* *`identifier`* <sub>необ.</sub> **`{`** *`struct-declaration-list`* **`}`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`struct-or-union`* *`identifier`*

*`struct-or-union`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`struct`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`union`**

*`struct-declaration-list`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`struct-declaration`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`struct-declaration-list`* *`struct-declaration`*

*`struct-declaration`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`specifier-qualifier-list`* *`struct-declarator-list`* **`;`**

*`specifier-qualifier-list`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`type-specifier`* *`specifier-qualifier-list`* <sub>необ.</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`type-qualifier`* *`specifier-qualifier-list`* <sub>необ.</sub>

*`struct-declarator-list`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`struct-declarator`* *`struct-declarator-list`* **`,`** *`struct-declarator`*

*`struct-declarator`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`declarator`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`type-specifier`* *`declarator`* <sub>необ.</sub> **`:`** *`constant-expression`*

*`parameter-declaration`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`declaration-specifiers`* *`declarator`*  /\* Именованный оператор объявления \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`declaration-specifiers`* *`abstract-declarator`* <sub>необ.</sub> /\* Анонимный оператор объявления \*/

*`identifier-list`* : /\* Для оператора объявления старого стиля \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`identifier`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`identifier-list`* **`,`** *`identifier`*

*`abstract-declarator`* : /\* Используется с анонимными операторами объявления \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`pointer`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`pointer`* <sub>необ.</sub> *`direct-abstract-declarator`*

*`direct-abstract-declarator`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`(`** *`abstract-declarator`* **`)`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`direct-abstract-declarator`* <sub>необ.</sub> **`[`** *`constant-expression`* <sub>необ.</sub> **`]`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`direct-abstract-declarator`* <sub>необ.</sub> **`(`** *`parameter-type-list`* <sub>необ.</sub> **`)`**

*`initializer`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`assignment-expression`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`{`** *`initializer-list`* **`}`**  /\* Для агрегатной инициализации \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`{`** *`initializer-list`* **`, }`**

*`initializer-list`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`initializer`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`initializer-list`* **`,`** *`initializer`*

*`type-name`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`specifier-qualifier-list`* *`abstract-declarator`* <sub>необ.</sub>

*`typedef-name`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`identifier`*

*`extended-decl-modifier-seq`* :&nbsp;&nbsp;&nbsp;&nbsp;/\* Только для систем Майкрософт \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`extended-decl-modifier`* <sub>необ.</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`extended-decl-modifier-seq`* *`extended-decl-modifier`*

*`extended-decl-modifier`* :&nbsp;&nbsp;&nbsp;&nbsp;/\* Только для систем Майкрософт \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`thread`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`naked`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`dllimport`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`dllexport`**

## <a name="see-also"></a>См. также

[Соглашения о вызовах](../cpp/calling-conventions.md)<br/>
[Грамматика структуры фразы](../c-language/phrase-structure-grammar.md)<br/>
[Устаревшие соглашения о вызовах](../cpp/obsolete-calling-conventions.md)
