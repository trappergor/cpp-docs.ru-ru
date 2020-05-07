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
ms.openlocfilehash: 3daf5dd5f9912194fd5d8aaeb4c7a312be142b69
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825353"
---
# <a name="o1-o2-minimize-size-maximize-speed"></a>/O1, /O2 (минимизировать размер, максимизировать скорость)

Выбирает предопределенный набор параметров, которые влияют на размер и скорость созданного кода.

## <a name="syntax"></a>Синтаксис

> Включения
> /O2

## <a name="remarks"></a>Примечания

Параметры компилятора **/O1** и **/O2** позволяют быстро задать несколько отдельных параметров оптимизации. Параметр **/O1** задает отдельные параметры оптимизации, которые создают наименьший код в большинстве случаев. Параметр **/O2** задает параметры, создающие самый быстрый код в большинстве случаев. Параметр **/O2** используется по умолчанию для сборок выпуска. В этой таблице показаны конкретные параметры, заданные параметрами **/O1** и **/O2**.

|Параметр|Эквивалент|
|------------|-------------------|
|**/O1** (уменьшение размера)|[/Og](og-global-optimizations.md) [/OS](os-ot-favor-small-code-favor-fast-code.md) [/Oy](oy-frame-pointer-omission.md) [/Ob2](ob-inline-function-expansion.md) [/GF](gf-eliminate-duplicate-strings.md) [/Gy](gy-enable-function-level-linking.md)|
|**/O2** (максимизировать скорость)|[/Og](og-global-optimizations.md) [/Oi](oi-generate-intrinsic-functions.md) [/OT](os-ot-favor-small-code-favor-fast-code.md) [/Oy](oy-frame-pointer-omission.md) [/Ob2](ob-inline-function-expansion.md) [/GF](gf-eliminate-duplicate-strings.md) [/Gy](gy-enable-function-level-linking.md)|

**/O1** и **/O2** являются взаимоисключающими.

> [!NOTE]
> **Только для x86**\
> Эти параметры подразумевают использование параметра подавление указателя кадра ([/Oy](oy-frame-pointer-omission.md)).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. В разделе **Свойства конфигурации**откройте **C/C++** и выберите страницу свойств **Оптимизация** .

1. Измените свойство **Оптимизация** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры/o (оптимизация кода)](o-options-optimize-code.md)<br/>
[Параметры компилятора КОМПИЛЯТОРОМ MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)<br/>
[/EH (модель обработки исключений)](eh-exception-handling-model.md)
