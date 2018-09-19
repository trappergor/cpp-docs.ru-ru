---
title: __declspec | Документация Майкрософт
ms.custom: ''
ms.date: 1/23/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __declspec_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++]
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b159bcdae6e7f576ed92275ec5f79d25132b53e5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111327"
---
# <a name="declspec"></a>__declspec

**Блок, относящийся только к системам Microsoft**

Расширенный синтаксис атрибутов для указания класса хранения использует сведения **__declspec** ключевое слово, которое указывает, что экземпляр заданного типа будет храниться с атрибутом класса хранения характерные для Майкрософт, перечисленные ниже. Примеры других модификаторов класса хранения **статический** и **extern** ключевые слова. Однако эти ключевые слова — часть спецификации ANSI языков C и C++, и как таковые они не описаны расширенным синтаксисом атрибутов. Расширенный синтаксис атрибутов упрощает и стандартизирует расширения для систем Microsoft в соответствии с правилами языков C и С++.

## <a name="grammar"></a>Грамматика

*спецификатор decl*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__declspec (***extended-decl-modifier-seq***)** 

*extended-decl-modifier-seq*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*extended-decl-modifier*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Extended-decl-modifier* *extended-decl-modifier-seq*

*extended-decl-modifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Выровнять (** *#* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**выделить («** *segname* **")**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**домен приложения**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**code_seg("** *segname* **")**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Устарело**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**jitintrinsic**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**naked**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noalias**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noinline**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noreturn**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**nothrow**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**novtable**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Процесс**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**свойство (** { **получить =**_get_func_name_ &#124; **, put =**_put_func_name_ } **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**ограничения**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**safebuffers**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**selectany**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**spectre(nomitigation)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**thread**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**UUID («** *ComObjectGUID* **")**

Пробел отделяет последовательность модификаторов объявления. Примеры приведены в дальнейших разделах.

Эти атрибуты класса хранения характерные для Майкрософт поддерживаются грамматикой расширенный атрибут: [выровнять](../cpp/align-cpp.md), [выделить](../cpp/allocate.md), [appdomain](../cpp/appdomain.md), [code_seg](../cpp/code-seg-declspec.md), [устаревшим](../cpp/deprecated-cpp.md), [dllexport](../cpp/dllexport-dllimport.md), [dllimport](../cpp/dllexport-dllimport.md), [jitintrinsic](../cpp/jitintrinsic.md), [сатрибутомnaked](../cpp/naked-cpp.md), [noalias](../cpp/noalias.md), [noinline](../cpp/noinline.md), [noreturn](../cpp/noreturn.md), [nothrow](../cpp/nothrow-cpp.md), [novtable](../cpp/novtable.md) , [процесс](../cpp/process.md), [ограничить](../cpp/restrict.md), [safebuffers](../cpp/safebuffers.md), [selectany](../cpp/selectany.md), [spectre](../cpp/spectre.md), и [поток](../cpp/thread.md). Она также поддерживает эти атрибуты COM-объекта: [свойство](../cpp/property-cpp.md) и [uuid](../cpp/uuid-cpp.md).

**Code_seg**, **dllexport**, **dllimport**, **с атрибутом naked**, **noalias**, **nothrow** , **свойство**, **ограничить**, **selectany**, **поток**, и **uuid**атрибуты класса хранения это свойства исключительно объявления объекта или функции, к которому они применяются. **Поток** атрибут влияет на данные и только объекты. **С атрибутом naked** и **spectre** атрибуты влияют на функции только. **Dllimport** и **dllexport** атрибуты влияют на функции, данные и объекты. **Свойство**, **selectany**, и **uuid** атрибуты влияют на COM-объекты.

**__Declspec** ключевые слова, которые должны размещаться в начале простого объявления. Компилятор игнорирует без предупреждения все **__declspec** ключевые слова помещаются после * или & и перед идентификатором переменной в объявлении.

Объект **__declspec** атрибут, указанный в начале объявления пользовательского типа относится к переменной этого типа. Пример:

```cpp
__declspec(dllimport) class X {} varX;
```

В этом случае атрибут применяется к `varX`. Объект **__declspec** атрибут размещается после **класс** или **структуры** применяется ключевое слово для определяемого пользователем типа. Пример:

```cpp
class __declspec(dllimport) X {};
```

В этом случае атрибут применяется к `X`.

Общие рекомендации по использованию **__declspec** атрибут для простых объявлений выглядит следующим образом:

*decl-specifier-seq* *init-declarator-list*;

*Decl-specifier-seq* должно содержать, помимо прочего, базовый тип (например **int**, **float**, **typedef**, или имя класса), класс хранения (например **статический**, **extern**), или **__declspec** расширения. *Init-declarator-list* должно содержать, помимо прочего, часть указателя объявлений. Пример:

```cpp
__declspec(selectany) int * pi1 = 0;   //Recommended, selectany & int both part of decl-specifier
int __declspec(selectany) * pi2 = 0;   //OK, selectany & int both part of decl-specifier
int * __declspec(selectany) pi3 = 0;   //ERROR, selectany is not part of a declarator
```

В следующем примере кода объявлена целочисленная локальная переменная потока и инициализирована с использованием следующего значения:

```cpp
// Example of the __declspec keyword
__declspec( thread ) int tls_i = 1;
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Расширенные атрибуты классов хранения в C](../c-language/c-extended-storage-class-attributes.md)