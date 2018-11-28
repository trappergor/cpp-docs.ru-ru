---
title: /Oy (подавление указателей фрейма)
ms.date: 11/19/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.OmitFramePointers
- /oy
helpviewer_keywords:
- omit frame pointer
- Oy compiler option [C++]
- stack frame pointer compiler option [C++]
- -Oy compiler option [C++]
- frame pointer omission compiler option [C++]
- suppress frame pointer creation
- /Oy compiler option [C++]
ms.assetid: c451da86-5297-4c5a-92bc-561d41379853
ms.openlocfilehash: 343b0e026c2932e97d4a8d4472ba2035d6302661
ms.sourcegitcommit: 3da2cb3ec85e77ddfd4d2a55edb133d580ce4f18
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2018
ms.locfileid: "52330394"
---
# <a name="oy-frame-pointer-omission"></a>/Oy (подавление указателей фрейма)

Отменяет создание указателей на фреймы в стеке вызовов.

## <a name="syntax"></a>Синтаксис

> /Oy [-]

## <a name="remarks"></a>Примечания

Этот параметр повышает скорость вызова функций, поскольку при этом не требуется создавать и удалять указатели фрейма. Кроме того, он высвобождается один регистр для общего использования.

**/Oy** включает подавление указателей фрейма и **/Oy-** отключает пропуск. X64 компиляторы, **/Oy** и **/Oy-** недоступны.

Если код требует адресацию на основе кадров, можно указать **/Oy-** параметр после **/Ox** параметр или используйте [оптимизировать](../../preprocessor/optimize.md) с "**y**"и **off** аргументы, чтобы добиться максимальной оптимизации с адресацию на основе кадров. Компилятор выявляет большинство ситуаций, где необходима адресацию на основе кадров (например, с помощью `_alloca` и `setjmp` функции и обработке структурированных исключений).

[/Ox (Включение наиболее видов оптимизации скорости)](../../build/reference/ox-full-optimization.md) и [/O1, / O2 (минимизировать размер, максимизировать скорость)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) параметры подразумевают **/Oy**. Указание **/Oy-** после **/Ox**, **/O1**, или **/O2** параметр отключает **/Oy**, будь то явно или неявно.

**/Oy** делает параметр компилятора, с помощью отладчика, поскольку компилятор подавляет информацию об указателях фрейма. При указании параметра компилятора отладочного ([/Z7, / Zi, /ZI](../../build/reference/z7-zi-zi-debug-information-format.md)), мы рекомендуем указывать **/Oy-** параметр после всех остальных параметров оптимизации компилятора.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **оптимизации** страницу свойств.

1. Изменить **опустить указатели на фреймы** свойство. Это свойство добавляет или удаляет только **/Oy** параметр. Если вы хотите добавить **/Oy-** выберите **командной строки** свойство странице и изменения **Дополнительные параметры**.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>.

## <a name="see-also"></a>См. также

[Параметры /O (оптимизация кода)](../../build/reference/o-options-optimize-code.md)<br/>
[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
