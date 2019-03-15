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
ms.openlocfilehash: 7884f52cc22766c6b1a864fc01abcd73f92cfabb
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57817963"
---
# <a name="oy-frame-pointer-omission"></a>/Oy (подавление указателей фрейма)

Отменяет создание указателей на фреймы в стеке вызовов.

## <a name="syntax"></a>Синтаксис

> /Oy [-]

## <a name="remarks"></a>Примечания

Этот параметр повышает скорость вызова функций, поскольку при этом не требуется создавать и удалять указатели фрейма. Кроме того, он высвобождается один регистр для общего использования.

**/Oy** включает подавление указателей фрейма и **/Oy-** отключает пропуск. X64 компиляторы, **/Oy** и **/Oy-** недоступны.

Если код требует адресацию на основе кадров, можно указать **/Oy-** параметр после **/Ox** параметр или используйте [оптимизировать](../../preprocessor/optimize.md) с "**y**"и **off** аргументы, чтобы добиться максимальной оптимизации с адресацию на основе кадров. Компилятор выявляет большинство ситуаций, где необходима адресацию на основе кадров (например, с помощью `_alloca` и `setjmp` функции и обработке структурированных исключений).

[/Ox (Включение наиболее видов оптимизации скорости)](ox-full-optimization.md) и [/O1, / O2 (минимизировать размер, максимизировать скорость)](o1-o2-minimize-size-maximize-speed.md) параметры подразумевают **/Oy**. Указание **/Oy-** после **/Ox**, **/O1**, или **/O2** параметр отключает **/Oy**, будь то явно или неявно.

**/Oy** делает параметр компилятора, с помощью отладчика, поскольку компилятор подавляет информацию об указателях фрейма. При указании параметра компилятора отладочного ([/Z7, / Zi, /ZI](z7-zi-zi-debug-information-format.md)), мы рекомендуем указывать **/Oy-** параметр после всех остальных параметров оптимизации компилятора.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **оптимизации** страницу свойств.

1. Изменить **опустить указатели на фреймы** свойство. Это свойство добавляет или удаляет только **/Oy** параметр. Если вы хотите добавить **/Oy-** выберите **командной строки** свойство странице и изменения **Дополнительные параметры**.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>.

## <a name="see-also"></a>См. также

[Параметры /O (оптимизация кода)](o-options-optimize-code.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
