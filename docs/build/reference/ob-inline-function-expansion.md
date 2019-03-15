---
title: Параметр /Ob (расширение встроенных функций)
ms.date: 09/25/2017
f1_keywords:
- VC.Project.VCCLWCECompilerTool.InlineFunctionExpansion
- VC.Project.VCCLCompilerTool.InlineFunctionExpansion
- /ob
helpviewer_keywords:
- inline functions, function expansion compiler option [C++]
- -Ob1 compiler option [C++]
- -Ob0 compiler option [C++]
- /Ob0 compiler option [C++]
- /Ob1 compiler option [C++]
- any suitable compiler option [C++]
- Ob2 compiler option [C++]
- Ob1 compiler option [C++]
- /Ob2 compiler option [C++]
- Ob compiler option [C++]
- -Ob2 compiler option [C++]
- disable compiler option [C++]
- -Ob compiler option [C++]
- /Ob compiler option [C++]
- only __inline compiler option [C++]
- Ob0 compiler option [C++]
- inline expansion, compiler option
ms.assetid: f134e6df-e939-4980-a01d-47425dbc562a
ms.openlocfilehash: 6bf16e5725916e81e64d80c0a1f96bf502c8826c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807523"
---
# <a name="ob-inline-function-expansion"></a>Параметр /Ob (расширение встроенных функций)

Управляет подстановкой функций.

## <a name="syntax"></a>Синтаксис

> /OB {0 | 1 | 2}

## <a name="arguments"></a>Аргументы

**0**<br/>
Отключает подставляемые функции. По умолчанию, раскрытие выполняется по решению компилятора и все функции, часто называют *Автоподстановка*.

**1**<br/>
Разрешает подстановку только из функций с пометкой [встроенного](../../cpp/inline-functions-cpp.md), `__inline`, или `__forceinline`, или в функции-члене C++ определены в объявлении класса.

**2**<br/>
Значение по умолчанию. Разрешает подстановку всех функций, помеченных как `inline`, `__inline` или `__forceinline`, а также любых функций, выбранных компилятором.

**/ Ob2** вступает в силу, когда [/O1, / O2 (минимизировать размер, максимизировать скорость)](o1-o2-minimize-size-maximize-speed.md) или [/Ox (Включение наиболее видов оптимизации скорости)](ox-full-optimization.md) используется.

Этот параметр необходимо включить оптимизацию с помощью **/O1**, **/O2**, **/Ox**, или **/Og**.

## <a name="remarks"></a>Примечания

Параметры и ключевые слова подстановки компилятор обрабатывает как рекомендации. Подстановка какой-либо функции не гарантируется. Подстановку можно отключить, но вы не сможете выполнить принудительную подстановку определенной функции компилятором, даже если используете ключевое слово `__forceinline`.

Можно использовать `#pragma` [auto_inline](../../preprocessor/auto-inline.md) директиву, чтобы исключить из рассмотрения как кандидаты на подстановку функции. Также см. в разделе `#pragma` [внутренние](../../preprocessor/intrinsic.md) директива.

> [!NOTE]
> Сведения, собранные из теста профилирования, запускают переопределения оптимизаций, которые бы в противном случае вступят в силу, если указать **/Ob**, **/Os**, или **/Ot**. Дополнительные сведения см. в разделе [профильной оптимизации](../profile-guided-optimizations.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Разверните **свойства конфигурации**, **C/C++** и выберите **оптимизации**.

1. Изменить **подставляемых функций** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.InlineFunctionExpansion%2A>.

## <a name="see-also"></a>См. также

[Параметры /O (оптимизация кода)](o-options-optimize-code.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
