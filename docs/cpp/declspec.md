---
title: __declspec
ms.date: 03/21/2019
f1_keywords:
- __declspec_cpp
- __declspec
- _declspec
helpviewer_keywords:
- __declspec keyword [C++]
ms.openlocfilehash: e0c99ea9379aa6e29096250e8bd36ce3d4f183e8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180229"
---
# <a name="__declspec"></a>__declspec

**Блок, относящийся только к системам Microsoft**

В синтаксисе расширенных атрибутов для указания сведений о классе хранения используется ключевое слово **__declspec** , которое указывает, что экземпляр заданного типа должен храниться в указанном ниже атрибуте класса хранения, связанном с Майкрософт. Примеры других модификаторов класса хранения включают ключевые слова **static** и **extern** . Однако эти ключевые слова — часть спецификации ANSI языков C и C++, и как таковые они не описаны расширенным синтаксисом атрибутов. Расширенный синтаксис атрибутов упрощает и стандартизирует расширения для систем Microsoft в соответствии с правилами языков C и С++.

## <a name="grammar"></a>Грамматика

*описатель decl*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__declspec (** *Extended-decl-Modifiers-seq* **)**

*extended-decl-modifier-seq*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*extended-decl-modifier*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;Extended- *decl-* модификатор *Extended-decl-модификатор-seq*

*extended-decl-modifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**выровняйте (** *#* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**выделение ("** *сегнаме* **")**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**распределителя**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**AppDomain**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**code_seg ("** *сегнаме* **")**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;не **рекомендуется**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**житинтринсик**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**naked**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**псевдонима**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noinline**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**return**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**throw**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**неvtable**<br/>
&nbsp;&nbsp;&nbsp;**процесса** &nbsp;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**свойство (** { **Get =** _get_func_name_ &#124; **, WHERE =** _put_func_name_ } **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**ограничения**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**сафебуфферс**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**selectany**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**устранением рисков Spectre (устранение рисков)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**thread**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**UUID ("** *комобжектгуид* **")**

Пробел отделяет последовательность модификаторов объявления. Примеры приведены в дальнейших разделах.

Грамматика расширенных атрибутов поддерживает следующие атрибуты класса хранения, предназначенные для Майкрософт: [выровняйте](../cpp/align-cpp.md), [выделение](../cpp/allocate.md), [распределитель](../cpp/allocator.md), [AppDomain](../cpp/appdomain.md), [code_seg](../cpp/code-seg-declspec.md), [устаревший](../cpp/deprecated-cpp.md), [dllexport](../cpp/dllexport-dllimport.md), [DllImport](../cpp/dllexport-dllimport.md), [житинтринсик](../cpp/jitintrinsic.md), [naked](../cpp/naked-cpp.md) [, InAttribute,](../cpp/noalias.md) [noinline](../cpp/noinline.md), [noreturn](../cpp/noreturn.md), [unthrow](../cpp/nothrow-cpp.md) [, InAttribute,](../cpp/novtable.md) [Process](../cpp/process.md), [restrict](../cpp/restrict.md), [сафебуфферс](../cpp/safebuffers.md), [selectany](../cpp/selectany.md), [ устранением рисков Spectre](../cpp/spectre.md)и [Thread](../cpp/thread.md). Он также поддерживает следующие атрибуты COM-объектов: [свойство](../cpp/property-cpp.md) и [UUID](../cpp/uuid-cpp.md).

Атрибуты класса хранения **code_seg**, **dllexport**, **DllImport**, **naked**, **Alias**, **unthrow**, **Property**, **restrict**, **selectany**, **Thread**и **UUID** являются свойствами только объявления объекта или функции, к которой они применяются. Атрибут **Thread** влияет только на данные и объекты. Атрибуты **naked** и **устранением рисков Spectre** влияют только на функции. Атрибуты **DllImport** и **dllexport** влияют на функции, данные и объекты. Атрибуты **Property**, **selectany**и **UUID** влияют на COM-объекты.

Для совместимости с предыдущими версиями **_declspec** является синонимом для **__declspec** , если только не указан параметр компилятора [/Za \(отключить расширения языка)](../build/reference/za-ze-disable-language-extensions.md) .

Ключевые слова **__declspec** должны располагаться в начале простого объявления. Компилятор игнорирует, без предупреждения, все **__declspec** ключевые слова, помещенные после * или & и перед идентификатором переменной в объявлении.

Атрибут **__declspec** , указанный в начале объявления определяемого пользователем типа, применяется к переменной этого типа. Пример:

```cpp
__declspec(dllimport) class X {} varX;
```

В этом случае атрибут применяется к `varX`. Атрибут **__declspec** , помещаемый после ключевого слова **Class** или **struct** , применяется к определяемому пользователем типу. Пример:

```cpp
class __declspec(dllimport) X {};
```

В этом случае атрибут применяется к `X`.

Общая рекомендация по использованию атрибута **__declspec** для простых объявлений выглядит следующим образом:

*описателе-описатель-seq* *init-декларатор-List*;

*Описатель decl-seq* должен содержать, помимо прочего, базовый тип (например, **int**, **float**, **typedef**или имя класса), класс хранения (например, **static**, **extern**) или расширение **__declspec** . Элемент *init-декларатор-List* должен содержать, помимо прочего, указательную часть объявлений. Пример:

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

## <a name="see-also"></a>См. также раздел

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Расширенные атрибуты классов хранения в C](../c-language/c-extended-storage-class-attributes.md)
