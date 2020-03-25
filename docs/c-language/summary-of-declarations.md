---
title: Общие сведения об объявлениях
ms.date: 11/04/2016
ms.assetid: 53a5e9e5-1a33-40b5-9dea-7f669b479329
ms.openlocfilehash: e553f4bdfffcd4bba6a39b2d37af6ba25a3d65d9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170440"
---
# <a name="summary-of-declarations"></a>Общие сведения об объявлениях

*declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*объявления-описатели* *attribute-seq*<sub>неявное</sub> *init-декларатор-List*<sub>OPT</sub> **;**

*declaration-specifiers*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*спецификаторы объявлений*<sub>opt</sub> *класса хранения*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;спецификаторы *объявления*<sub>opt</sub> *спецификатора типа*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*спецификаторы объявления*<sub>opt</sub> *квалификаторов типа*

*attribute-seq* :&nbsp;&nbsp;&nbsp;&nbsp;/\* \*/<br/>
атрибут *атрибута* &nbsp;&nbsp;&nbsp;&nbsp; *-Seq*<sub>OPT</sub>

*атрибут* : один из&nbsp;&nbsp;&nbsp;&nbsp;/\* \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;[__asm](../assembler/inline/asm.md) [__clrcall](../cpp/clrcall.md) [__stdcall](../cpp/stdcall.md) [__based](../cpp/based-grammar.md) [__fastcall](../cpp/fastcall.md) [__thiscall](../cpp/thiscall.md) [__cdecl](../cpp/cdecl.md) [__inline](../cpp/inline-functions-cpp.md) [__vectorcall](../cpp/vectorcall.md)

*init-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-декларатор-List* **,** *декларатор*

*init-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*декларатор* **=** *инициализатор* /\* для скалярной инициализации \*/

*storage-class-specifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**auto**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**register**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**static**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**extern**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**typedef**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__declspec (** *Extended-decl-Modifiers-seq* **)**  /\* \*, относящегося к Microsoft /

*type-specifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**void**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**char**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**short**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**int**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int8** /\* \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int16** /\* \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int32** /\* \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int64** /\* \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**long**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**float**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**double**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**signed**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**unsigned**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-or-union-specifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enum-specifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*typedef-name*

*type-qualifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**const**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**volatile**

*declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<sub>opt</sub> *прямого объявления* *указателя*

*direct-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **(** *декларатор* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*прямого объявления* **[** *константное выражение*<sub>OPT</sub> **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*прямого объявления* **(** *parameter-type-List* **)**  /\* декларатора нового стиля \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*прямого объявления* **(** *идентификатор-списка*<sub>OPT</sub> **)**  /\* декларатора устаревшего стиля \*/

*pointer*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> - *квалификатор, список*<sub>необязательностей</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> <sub>необязательное</sub> *pointer* отображение *списка квалификаторов типа*

*parameter-type-list*:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/\* Список параметров \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-list*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *-список параметров* **,...**

*parameter-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *-список параметров* **,** *объявление параметров*

*type-qualifier-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-qualifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;- *квалификатор типа* *списка*

*enum-specifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**идентификатор перечисления** *identifier*<sub>OPT</sub> **{** *перечислитель-List* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**enum** *идентификатор* перечисления

*enumerator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enumerator*<br/>
&nbsp;&nbsp;&nbsp;*перечислителя &nbsp;-List* **,** *Enumerator*

*enumerator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enumeration-constant*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*перечисление константы* **=** *константное выражение*

*enumeration-constant*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*

*спецификатор-структуры-или-объединения*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*структуры-or-Union* *идентификатор*<sub>OPT</sub> **{** *struct-объявление-List* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*структуру или* *идентификатор* объединения

*структура-или-объединение*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**struct**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**union**

*список-объявлений-структуры*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-declaration*<br/>
&nbsp;&nbsp; *&nbsp;&nbsp;-* *объявление* структуры в виде структуры

*объявление-структуры*:<br/>
&nbsp;&nbsp;&nbsp;*описатель квалификатора* &nbsp;-List-список *деклараторов* -список **;**

*список-спецификаторов-и-квалификаторов*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;описателе описателей *типа* - *квалификатор-List*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;описателе *квалификаторов типа* - *квалификатор-List*<sub>opt</sub>

*список-деклараторов-структуры*:<br/>
&nbsp;&nbsp; *&nbsp;&nbsp;структуры декларатор структуры-* *декларатора* **,** *декларатор структуры*

*декларатор-структуры*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*декларатор*<sub>opt</sub> *спецификатора типа* **:** *константное выражение*

*parameter-declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*декларатор* *описателей* /\* с именем декларатор \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers* *абстрактные*описатели — объявление<sub>OPT</sub> /\* анонимного декларатора \*/

*identifier-list*: /\* Для декларатора устаревшего стиля \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*идентификатор-список* **,** *идентификатор*

*abstract-declarator*: /\* Используется с анонимными деклараторами \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*pointer*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*указателями*прямого и<sub>неявного</sub> - *абстрактного-декларатора*

*direct-abstract-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **(** *абстрактное объявление* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-abstract-декларатор*<sub>OPT</sub> **[** *константное выражение*<sub>OPT</sub> **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-abstract-декларатор*<sub>OPT</sub> **(** *параметр-Type-List*<sub>OPT</sub> **)**

*initializer*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*assignment-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **{** *initializer-List* **}**  /\* для агрегатной инициализации \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **{** *initializer-List* **,}**

*initializer-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*initializer*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*инициализатор-списка* **,** *инициализатор*

*type-name*:<br/>
&nbsp;&nbsp;&nbsp;*описатель квалификатора &nbsp;-List* *abstract-декларатор*<sub>opt</sub>

*typedef-name*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*

*Extended-decl-модификатор-seq*:&nbsp;&nbsp;&nbsp;&nbsp;/\* \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*extended-decl-modifier*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Расширенный-decl-модификатор-seq* *Extended-decl-модификатор*

*Расширенный-decl-модификатор*:&nbsp;&nbsp;&nbsp;&nbsp;/\* \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**thread**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**naked**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**

## <a name="see-also"></a>См. также раздел

[Соглашения о вызовах](../cpp/calling-conventions.md)<br/>
[Грамматика структуры фразы](../c-language/phrase-structure-grammar.md)<br/>
[Устаревшие соглашения о вызовах](../cpp/obsolete-calling-conventions.md)
