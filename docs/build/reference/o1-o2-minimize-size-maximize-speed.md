---
title: -O1, - O2 (минимизировать размер, максимизировать скорость) | Документы Microsoft
ms.custom: ''
ms.date: 09/25/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /o2
- /o1
dev_langs:
- C++
helpviewer_keywords:
- maximize speed compiler option [C++]
- minimize size compiler option [C++]
- -O2 compiler option [C++]
- fast code
- small code
- O2 compiler option [C++]
- /O2 compiler option [C++]
- -O1 compiler option [C++]
- O1 compiler option [C++]
- /O1 compiler option [C++]
ms.assetid: 2d1423f5-53d9-44da-8908-b33a351656c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5003695c5ae2b16faf8aa80f68928858a3a48288
ms.sourcegitcommit: 4cdfff1114829599ab54178767f57664ad3424d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/20/2018
ms.locfileid: "36270556"
---
# <a name="o1-o2-minimize-size-maximize-speed"></a>/O1, /O2 (минимизировать размер, максимизировать скорость)

Можно выбрать стандартный набор параметров, влияющих на размер и скорость созданного кода.

## <a name="syntax"></a>Синтаксис

> /O1  
> /O2

## <a name="remarks"></a>Примечания

**/O1** и **/O2** параметры компилятора — это быстрый способ задать несколько особенные параметры оптимизации за один раз. **/O1** параметр задает параметры отдельных оптимизации, создать наименьший в большинстве случаев. **/O2** параметр задает параметры, создать быстрый код в большинстве случаев. **/O2** параметр выбирается по умолчанию для сборки выпуска. В этой таблице показаны конкретные параметры, которые задаются **/O1** и **/O2**:

|Параметр|Эквивалентно|
|------------|-------------------|
|**/ O1** (минимизировать размер)|[/Og](../../build/reference/og-global-optimizations.md) [/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) [/Oy](../../build/reference/oy-frame-pointer-omission.md) [/Ob2](../../build/reference/ob-inline-function-expansion.md) [/GF](../../build/reference/gf-eliminate-duplicate-strings.md) [/Gy](../../build/reference/gy-enable-function-level-linking.md)|
|**/ O2** (максимизировать скорость)|[/Og](../../build/reference/og-global-optimizations.md) [/Oi](../../build/reference/oi-generate-intrinsic-functions.md) [/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) [/Oy](../../build/reference/oy-frame-pointer-omission.md) [/Ob2](../../build/reference/ob-inline-function-expansion.md) [/GF](../../build/reference/gf-eliminate-duplicate-strings.md) [/Gy](../../build/reference/gy-enable-function-level-linking.md)|

**/ O1** и **/O2** являются взаимоисключающими.

> [!NOTE]  
> **x86 конкретных**  
> Эти параметры подразумевают использование подавление указателей фрейма ([/Oy](../../build/reference/oy-frame-pointer-omission.md)) параметра.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. В разделе **свойства конфигурации**откройте **C/C++** и выберите **оптимизации** страницу свойств.

1. Изменить **оптимизации** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>См. также

[Параметры /O (оптимизация кода)](../../build/reference/o-options-optimize-code.md)  
[Параметры компилятора](../../build/reference/compiler-options.md)  
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)  
[/EH (модель обработки исключений)](../../build/reference/eh-exception-handling-model.md)
