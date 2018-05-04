---
title: __declspec | Документы Microsoft
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
ms.openlocfilehash: c610da3545e7269c307542930140616dc6af9dce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="declspec"></a>__declspec

**Блок, относящийся только к системам Microsoft**

Расширенный синтаксис атрибутов для указания класса хранения использует сведения **__declspec** ключевое слово, которое указывает, что экземпляр заданного типа для хранения с атрибутом класса хранения характерные для Майкрософт, перечисленные ниже. Примеры других модификаторов класса хранения **статических** и **extern** ключевые слова. Однако эти ключевые слова — часть спецификации ANSI языков C и C++, и как таковые они не описаны расширенным синтаксисом атрибутов. Расширенный синтаксис атрибутов упрощает и стандартизирует расширения для систем Microsoft в соответствии с правилами языков C и С++.

## <a name="grammar"></a>Грамматика

*спецификатор decl*:  
&nbsp;&nbsp;&nbsp;&nbsp;**__declspec (***расширенных последовательность модификаторов объявления***)** 

*extended-decl-modifier-seq*:  
&nbsp;&nbsp;&nbsp;&nbsp;*модификатор расширенного объявления*<sub>необязательно</sub>  
&nbsp;&nbsp;&nbsp;&nbsp;*модификатор расширенного объявления* *расширенных последовательность модификаторов объявления*

*extended-decl-modifier*:  
&nbsp;&nbsp;&nbsp;&nbsp;**Выравнивание (** *#* **)**  
&nbsp;&nbsp;&nbsp;&nbsp;**выделить («** *segname* **»)**  
&nbsp;&nbsp;&nbsp;&nbsp;**домен приложения**  
&nbsp;&nbsp;&nbsp;&nbsp;**code_seg("** *segname* **")**  
&nbsp;&nbsp;&nbsp;&nbsp;**Рекомендуется использовать**  
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**  
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**  
&nbsp;&nbsp;&nbsp;&nbsp;**jitintrinsic**  
&nbsp;&nbsp;&nbsp;&nbsp;**naked**  
&nbsp;&nbsp;&nbsp;&nbsp;**noalias**  
&nbsp;&nbsp;&nbsp;&nbsp;**noinline**  
&nbsp;&nbsp;&nbsp;&nbsp;**noreturn**  
&nbsp;&nbsp;&nbsp;&nbsp;**nothrow**  
&nbsp;&nbsp;&nbsp;&nbsp;**novtable**  
&nbsp;&nbsp;&nbsp;&nbsp;**Процесс**  
&nbsp;&nbsp;&nbsp;&nbsp;**свойство (** { **получить =**_get_func_name_ &#124; **, put =**_put_func_name_ } **)**  
&nbsp;&nbsp;&nbsp;&nbsp;**Ограничения**  
&nbsp;&nbsp;&nbsp;&nbsp;**safebuffers**  
&nbsp;&nbsp;&nbsp;&nbsp;**selectany**  
&nbsp;&nbsp;&nbsp;&nbsp;**spectre(nomitigation)**  
&nbsp;&nbsp;&nbsp;&nbsp;**поток**  
&nbsp;&nbsp;&nbsp;&nbsp;**UUID («** *ComObjectGUID* **»)**  

Пробел отделяет последовательность модификаторов объявления. Примеры приведены в дальнейших разделах.

Эти атрибуты класса хранения Майкрософт поддерживаются грамматикой расширенный атрибут: [выравнивание](../cpp/align-cpp.md), [выделить](../cpp/allocate.md), [appdomain](../cpp/appdomain.md), [code_seg](../cpp/code-seg-declspec.md), [устаревшими](../cpp/deprecated-cpp.md), [dllexport](../cpp/dllexport-dllimport.md), [dllimport](../cpp/dllexport-dllimport.md), [jitintrinsic](../cpp/jitintrinsic.md), [naked](../cpp/naked-cpp.md), [noalias](../cpp/noalias.md), [noinline](../cpp/noinline.md), [noreturn](../cpp/noreturn.md), [nothrow](../cpp/nothrow-cpp.md), [novtable](../cpp/novtable.md) , [процесс](../cpp/process.md), [ограничить](../cpp/restrict.md), [safebuffers](../cpp/safebuffers.md), [selectany](../cpp/selectany.md), [spectre](../cpp/spectre.md), и [поток](../cpp/thread.md). Оно также поддерживает следующие атрибуты COM-объекта: [свойство](../cpp/property-cpp.md) и [uuid](../cpp/uuid-cpp.md).

**Code_seg**, **dllexport**, **dllimport**, **naked**, **noalias**, **nothrow** , **свойство**, **ограничить**, **selectany**, **поток**, и **uuid**атрибуты класса хранения это свойства исключительно объявления объекта или функции, к которому они применяются. **Поток** атрибут влияет на данные и только объектов. **Naked** и **spectre** атрибуты влияют на функции только. **Dllimport** и **dllexport** атрибуты влияют на функции, данные и объекты. **Свойство**, **selectany**, и **uuid** атрибуты влияют на COM-объекты.

**__Declspec** ключевые слова должны размещаться в начале простого объявления. Компилятор игнорирует без предупреждения все **__declspec** ключевые слова помещен после * или & и перед идентификатором переменной в объявлении.

Объект **__declspec** атрибут, указанный в начале объявления пользовательского типа относится к переменной этого типа. Пример:

```cpp
__declspec(dllimport) class X {} varX;
```

В этом случае атрибут применяется к `varX`. Объект **__declspec** атрибут помещен после **класса** или **структуры** применяется ключевое слово для определяемого пользователем типа. Пример:

```cpp
class __declspec(dllimport) X {};
```

В этом случае атрибут применяется к `X`.

Общие рекомендации по использованию **__declspec** атрибут для простых объявлений является следующим образом:

*decl-specifier-seq* *список деклараторов*;

*Decl-specifier-seq* должен содержать, помимо прочего, базовый тип (например **int**, **float**, **typedef**, или имя класса), класс хранения (например **статических**, **extern**), или **__declspec** расширения. *Список деклараторов* должен содержать, помимо прочего, часть объявления указателя. Пример:

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

[Ключевые слова](../cpp/keywords-cpp.md)  
[Расширенные атрибуты классов хранения в C](../c-language/c-extended-storage-class-attributes.md)  
