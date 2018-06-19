---
title: -Oy (подавление указателей фрейма) | Документы Microsoft
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
ms.openlocfilehash: b6feb682d364c4c40fd01e4aff33404c4506d9c1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377265"
---
# <a name="oy-frame-pointer-omission"></a>/Oy (подавление указателей фрейма)

Отменяет создание указателей на фреймы в стеке вызовов.

## <a name="syntax"></a>Синтаксис

> /Oy [-]

## <a name="remarks"></a>Примечания

Этот параметр повышает скорость вызова функций, поскольку при этом не требуется создавать и удалять указатели фрейма. Также для хранения часто используемых переменных и подвыражений высвобождается один регистр (EBP на процессорах Intel 386 или более поздних версиях).

**/Oy** включает подавление указателей фрейма и **/Oy-** отключает упущение. **/Oy** доступна только в x86 компиляторов.

Если код требует выполнения на основе EBP адресации, можно указать **/Oy-** параметр после **/ox** или [оптимизировать](../../preprocessor/optimize.md) с «**y**» и **off** аргументы, чтобы добиться максимальной оптимизации с учетом EBP адресацией. Компилятор выявляет большинство ситуаций, в которых требуется адресация с базой по регистру EBP (например, с функциями `_alloca` и `setjmp` или при обработке структурированных исключений).

[/Ox (включить наиболее скорость оптимизации)](../../build/reference/ox-full-optimization.md) и [/O1, / O2 (минимизировать размер, максимизировать скорость)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) параметры подразумевают **/Oy**. Указание **/Oy-** после **/ox**, **/O1**, или **/O2** параметр отключает **/Oy**, будь то явно или неявно.

**/Oy** делает параметр компилятора, с помощью отладчика, поскольку компилятор подавляет информацию об указателях фрейма. При указании используется отладочный параметр компилятора ([/Z7, / Zi, /ZI](../../build/reference/z7-zi-zi-debug-information-format.md)), мы рекомендуем указывать **/Oy-** параметр после всех остальных параметров оптимизации компилятора.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **оптимизации** страницу свойств.

1. Изменить **подавление указателей фрейма** свойство. Это свойство добавляет или удаляет только **/Oy** параметр. Если вы хотите добавить **/Oy-** , нажмите кнопку **командной строки** и изменения **Дополнительные параметры**.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>.

## <a name="see-also"></a>См. также

[Параметры /O (оптимизация кода)](../../build/reference/o-options-optimize-code.md)

[Параметры компилятора](../../build/reference/compiler-options.md)

[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)