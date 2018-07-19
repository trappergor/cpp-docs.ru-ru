---
title: -Ob (расширение встроенных функций) | Документы Microsoft
ms.custom: ''
ms.date: 09/25/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.InlineFunctionExpansion
- VC.Project.VCCLCompilerTool.InlineFunctionExpansion
- /ob
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb7c31dca2d95232850140576be3ddc0ac695cac
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377836"
---
# <a name="ob-inline-function-expansion"></a>Параметр /Ob (расширение встраиваемых функций)

Управляет подстановкой функций.

## <a name="syntax"></a>Синтаксис

> Параметр /OB {0 | 1 | 2}

## <a name="arguments"></a>Аргументы

**0**  
Отключает подставляемые функции. По умолчанию раскрытие выполняется по решению компилятора и все функции часто называют *Автоподстановка*.

**1**  
Разрешает подстановку только тех функций, помеченных как [встроенного](../../cpp/inline-functions-cpp.md), `__inline`, или `__forceinline`, или в функции-члене C++ определены в объявлении класса.

**2**  
Значение по умолчанию. Разрешает подстановку всех функций, помеченных как `inline`, `__inline` или `__forceinline`, а также любых функций, выбранных компилятором.

**/ Ob2** вступает в силу, когда [/O1, / O2 (минимизировать размер, максимизировать скорость)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) или [/Ox (включить наиболее скорость оптимизации)](../../build/reference/ox-full-optimization.md) используется.

Этот параметр необходимо включить оптимизацию с помощью **/O1**, **/O2**, **/ox**, или **/Og**.  

## <a name="remarks"></a>Примечания

Параметры и ключевые слова подстановки компилятор обрабатывает как рекомендации. Подстановка какой-либо функции не гарантируется. Подстановку можно отключить, но вы не сможете выполнить принудительную подстановку определенной функции компилятором, даже если используете ключевое слово `__forceinline`.

Можно использовать `#pragma` [auto_inline](../../preprocessor/auto-inline.md) директиву, чтобы исключить из рассмотрения как кандидаты на подстановку функции. См. также `#pragma` [встроенная функция](../../preprocessor/intrinsic.md) директивы.

> [!NOTE]
> Сведения, полученные из теста профилирования, запускают переопределения оптимизаций, которые в противном случае вступят в силу при указании **/Ob**, **/Os**, или **/Ot**. Дополнительные сведения см. в разделе [профильные оптимизации](../../build/reference/profile-guided-optimizations.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Разверните **свойства конфигурации**, **C/C++** и выберите **оптимизации**.

1. Изменить **подставляемых функций** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.InlineFunctionExpansion%2A>.

## <a name="see-also"></a>См. также

[Параметры /O (оптимизация кода)](../../build/reference/o-options-optimize-code.md)  
[Параметры компилятора](../../build/reference/compiler-options.md)  
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)