---
title: -Oy (подавление указателей фрейма) | Документация Майкрософт
ms.custom: ''
ms.date: 09/22/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.OmitFramePointers
- /oy
dev_langs:
- C++
helpviewer_keywords:
- omit frame pointer
- Oy compiler option [C++]
- stack frame pointer compiler option [C++]
- -Oy compiler option [C++]
- frame pointer omission compiler option [C++]
- suppress frame pointer creation
- /Oy compiler option [C++]
ms.assetid: c451da86-5297-4c5a-92bc-561d41379853
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6c077b5a350d7381adc5412ca4a318713d720ad6
ms.sourcegitcommit: 1870c342d44b10990fd015e60856225c3026e8c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2018
ms.locfileid: "49963055"
---
# <a name="oy-frame-pointer-omission"></a>/Oy (подавление указателей фрейма)

Отменяет создание указателей на фреймы в стеке вызовов.

## <a name="syntax"></a>Синтаксис

> /Oy [-]

## <a name="remarks"></a>Примечания

Этот параметр повышает скорость вызова функций, поскольку при этом не требуется создавать и удалять указатели фрейма. Кроме того, он высвобождается один регистр для общего использования.

**/Oy** включает подавление указателей фрейма и **/Oy-** отключает пропуск. **/Oy** доступна только в x86 компиляторов.

Если код требует адресацию на основе EBP, можно указать **/Oy-** параметр после **/Ox** параметр или используйте [оптимизировать](../../preprocessor/optimize.md) с "**y**" и **off** аргументы, чтобы добиться максимальной оптимизации с адресацию на основе EBP. Компилятор выявляет большинство ситуаций, в которых требуется адресация с базой по регистру EBP (например, с функциями `_alloca` и `setjmp` или при обработке структурированных исключений).

[/Ox (Включение наиболее видов оптимизации скорости)](../../build/reference/ox-full-optimization.md) и [/O1, / O2 (минимизировать размер, максимизировать скорость)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) параметры подразумевают **/Oy**. Указание **/Oy-** после **/Ox**, **/O1**, или **/O2** параметр отключает **/Oy**, будь то явно или неявно.

**/Oy** делает параметр компилятора, с помощью отладчика, поскольку компилятор подавляет информацию об указателях фрейма. При указании параметра компилятора отладочного ([/Z7, / Zi, /ZI](../../build/reference/z7-zi-zi-debug-information-format.md)), мы рекомендуем указывать **/Oy-** параметр после всех остальных параметров оптимизации компилятора.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **оптимизации** страницу свойств.

1. Изменить **опустить указатели на фреймы** свойство. Это свойство добавляет или удаляет только **/Oy** параметр. Если вы хотите добавить **/Oy-** нажмите **командной строки** и изменение **Дополнительные параметры**.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>.

## <a name="see-also"></a>См. также

[Параметры /O (оптимизация кода)](../../build/reference/o-options-optimize-code.md)

[Параметры компилятора](../../build/reference/compiler-options.md)

[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
