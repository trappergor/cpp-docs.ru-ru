---
title: /O1, /O2 (минимизировать размер, максимизировать скорость)
ms.date: 09/25/2017
f1_keywords:
- /o2
- /o1
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
ms.openlocfilehash: d33fe6bceae09267fd3f79ffe3dc26864e87c764
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820589"
---
# <a name="o1-o2-minimize-size-maximize-speed"></a>/O1, /O2 (минимизировать размер, максимизировать скорость)

Выбирает предустановленный набор параметров, влияющих на размер и скорость сформированного кода.

## <a name="syntax"></a>Синтаксис

> / O1/O2

## <a name="remarks"></a>Примечания

**/O1** и **/O2** параметры компилятора — это быстрый способ задать несколько особенные параметры оптимизации за один раз. **/O1** параметр задает параметры отдельных оптимизации, которые создают наименьший в большинстве случаев. **/O2** параметр задает параметры, создать быстрый код в большинстве случаев. **/O2** значение по умолчанию для сборок выпуска. Эта таблица показывает особые параметры, которые задаются **/O1** и **/O2**:

|Параметр|Эквивалентно|
|------------|-------------------|
|**/ O1** (минимизировать размер)|[/Og](og-global-optimizations.md) [/Os](os-ot-favor-small-code-favor-fast-code.md) [/Oy](oy-frame-pointer-omission.md) [/Ob2](ob-inline-function-expansion.md) [/GF](gf-eliminate-duplicate-strings.md) [/Gy](gy-enable-function-level-linking.md)|
|**/ O2** (максимизировать скорость)|[/Og](og-global-optimizations.md) [/Oi](oi-generate-intrinsic-functions.md) [/Ot](os-ot-favor-small-code-favor-fast-code.md) [/Oy](oy-frame-pointer-omission.md) [/Ob2](ob-inline-function-expansion.md) [/GF](gf-eliminate-duplicate-strings.md) [/Gy](gy-enable-function-level-linking.md)|

**/ O1** и **/O2** взаимно исключают друг друга.

> [!NOTE]
> **x86 конкретных** эти параметры подразумевают использование подавление указателей фрейма ([/Oy](oy-frame-pointer-omission.md)) параметр.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. В разделе **свойства конфигурации**откройте **C/C++** и выберите **оптимизации** страницу свойств.

1. Изменить **оптимизации** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>См. также

[Параметры /O (оптимизация кода)](o-options-optimize-code.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[/EH (модель обработки исключений)](eh-exception-handling-model.md)
