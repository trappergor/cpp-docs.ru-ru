---
title: __declspec
ms.date: 03/21/2019
f1_keywords:
- __declspec_cpp
- __declspec
- _declspec
helpviewer_keywords:
- __declspec keyword [C++]
ms.openlocfilehash: 945202beca6c5deb525bd19886b947331f6f3ac3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228951"
---
# `__declspec`

**Блок, относящийся только к системам Microsoft**

В синтаксисе расширенных атрибутов для указания сведений о классе хранения используется **`__declspec`** ключевое слово, которое указывает, что экземпляр заданного типа должен храниться в указанном ниже атрибуте класса хранения, связанном с Майкрософт. Примеры других модификаторов класса хранения включают **`static`** **`extern`** Ключевые слова и. Однако эти ключевые слова — часть спецификации ANSI языков C и C++, и как таковые они не описаны расширенным синтаксисом атрибутов. Расширенный синтаксис атрибутов упрощает и стандартизирует расширения для систем Microsoft в соответствии с правилами языков C и С++.

## <a name="grammar"></a>Грамматика

*описатель decl*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__declspec (`**  *Расширенный-decl-модификатор-Seq*  **`)`**

*Расширенный-decl-модификатор-seq*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*extended-decl-modifier*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Расширенный* -decl-модификатор *Extended-decl-модификатор-seq*

*Модификатор Extended-decl*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`align(`** *#* **`)`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`allocate("`***сегнаме***`")`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`allocator`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`appdomain`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`code_seg("`***сегнаме***`")`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`deprecated`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`dllimport`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`dllexport`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`jitintrinsic`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`naked`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`noalias`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`noinline`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`noreturn`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`nothrow`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`novtable`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`process`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`property(`**{ **`get=`** _get_func_name_ &#124; **`,put=`** _put_func_name_ }**`)`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`restrict`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`safebuffers`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`selectany`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`spectre(nomitigation)`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`thread`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`uuid("`***Комобжектгуид***`")`**

Пробел отделяет последовательность модификаторов объявления. Примеры приведены в дальнейших разделах.

Грамматика расширенных атрибутов поддерживает следующие атрибуты классов хранения, предназначенные для Майкрософт:,,,,,,,,,,,,,,,,,,, [`align`](../cpp/align-cpp.md) [`allocate`](../cpp/allocate.md) [`allocator`](../cpp/allocator.md) [`appdomain`](../cpp/appdomain.md) [`code_seg`](../cpp/code-seg-declspec.md) [`deprecated`](../cpp/deprecated-cpp.md) [`dllexport`](../cpp/dllexport-dllimport.md) [`dllimport`](../cpp/dllexport-dllimport.md) [`jitintrinsic`](../cpp/jitintrinsic.md) [`naked`](../cpp/naked-cpp.md) [`noalias`](../cpp/noalias.md) [`noinline`](../cpp/noinline.md) [`noreturn`](../cpp/noreturn.md) [`nothrow`](../cpp/nothrow-cpp.md) [`novtable`](../cpp/novtable.md) [`process`](../cpp/process.md) [`restrict`](../cpp/restrict.md) [`safebuffers`](../cpp/safebuffers.md) [`selectany`](../cpp/selectany.md) [`spectre`](../cpp/spectre.md) и [`thread`](../cpp/thread.md) . Он также поддерживает следующие атрибуты COM-Object: [`property`](../cpp/property-cpp.md) и [`uuid`](../cpp/uuid-cpp.md) .

**`code_seg`** **`dllexport`** **`dllimport`** Атрибуты класса хранения,,,,, **`naked`** **`noalias`** **`nothrow`** , **`property`** , **`restrict`** , **`selectany`** , **`thread`** и **`uuid`** являются свойствами только объявления объекта или функции, к которым они применяются. **`thread`** Атрибут влияет только на данные и объекты. **`naked`** Атрибуты и **`spectre`** влияют только на функции. **`dllimport`** Атрибуты и **`dllexport`** влияют на функции, данные и объекты. **`property`** Атрибуты, **`selectany`** и **уу'ид** влияют на COM-объекты.

Для совместимости с предыдущими версиями аргумент **`_declspec`** является синонимом, **`__declspec`** если только параметр компилятора [/Za не \( отключил расширения языка)](../build/reference/za-ze-disable-language-extensions.md) .

**`__declspec`** Ключевые слова должны располагаться в начале простого объявления. Компилятор игнорирует, без предупреждения, все **`__declspec`** Ключевые слова, помещенные после * или &, а также перед идентификатором переменной в объявлении.

**`__declspec`** Атрибут, указанный в начале объявления определяемого пользователем типа, применяется к переменной этого типа. Например:

```cpp
__declspec(dllimport) class X {} varX;
```

В этом случае атрибут применяется к `varX`. **`__declspec`** Атрибут, помещенный после **`class`** **`struct`** ключевого слова или, применяется к определяемому пользователем типу. Например:

```cpp
class __declspec(dllimport) X {};
```

В этом случае атрибут применяется к `X`.

Ниже приведены общие рекомендации по использованию **`__declspec`** атрибута для простых объявлений.

*описателе-описатель-seq* *init-декларатор-List*;

*Описатель decl-seq* должен содержать, помимо прочего, базовый тип (например,, **`int`** **`float`** **`typedef`** или имя класса), класс хранения (например **`static`** , **`extern`** ) или **`__declspec`** расширение. Элемент *init-декларатор-List* должен содержать, помимо прочего, указательную часть объявлений. Например:

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
