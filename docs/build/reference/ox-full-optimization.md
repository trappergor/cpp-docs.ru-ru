---
title: "-Ox (включить большинство видов оптимизации скорости) | Документы Microsoft"
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.ToolOptimization
- /ox
dev_langs:
- C++
helpviewer_keywords:
- Ox compiler option [C++]
- fast code [C++]
- /Ox compiler option [C++]
- -Ox compiler option [C++]
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 85efa8a2beab34d0dcf1bdb74e3cf89008b10d6e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ox-enable-most-speed-optimizations"></a>/Ox (включить большинство видов оптимизации скорости)

**/Ox** сочетание оптимизации, которые предпочитать скорость включает параметр компилятора. В некоторых версиях Visual Studio IDE и компилятора справочное сообщение, это называется *Полная оптимизация*, но **/ox** только подмножество параметров оптимизации скорости, включаемые включает параметр компилятора **/O2**.

## <a name="syntax"></a>Синтаксис

> /Ox

## <a name="remarks"></a>Примечания

**/Ox** включает параметр компилятора **/o** эта скорость favor параметры компилятора. **/Ox** не поддерживает дополнительный параметр компилятора [/GF (исключить повторяющиеся строки)](../../build/reference/gf-eliminate-duplicate-strings.md) и [/Gy (включение компоновки на уровне функций)](../../build/reference/gy-enable-function-level-linking.md) параметры, доступные при [/O1 или/O2 (минимизировать размер, максимизировать скорость)](../../build/reference/o1-o2-minimize-size-maximize-speed.md). Дополнительные параметры, примененное **/O1** и **/O2** может привести к указатели на строки или функции для общего целевого адреса, что может повлиять на отладку и строгой языковой совместимости. **/Ox** параметр — простой способ включения большинство видов оптимизации без включения **/GF** и **/Gy**. Дополнительные сведения см. в разделе описания [/GF](../../build/reference/gf-eliminate-duplicate-strings.md) и [/Gy](../../build/reference/gy-enable-function-level-linking.md) параметры.

**/Ox** параметр компилятора совпадает с помощью следующих параметров в сочетании:

- [Параметр /Ob (расширение встроенных функций)](../../build/reference/ob-inline-function-expansion.md), где параметр — 2 (**/Ob2**)

- [/Og (виды глобальной оптимизации)](../../build/reference/og-global-optimizations.md)

- [/Oi (Создание встроенных функций)](../../build/reference/oi-generate-intrinsic-functions.md)

- [/Ot (приоритет быстрого кода)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)

- [/Oy (подавление указателей фрейма)](../../build/reference/oy-frame-pointer-omission.md)

**/ Ox** является взаимоисключающим с:

- [/ O1 (Уменьшение размера)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)

- [/ O2 (максимизировать скорость)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)

- [/OD (Выключение (отладчика))](../../build/reference/od-disable-debug.md)

Вы можете отменить смещения в сторону скорость **/ox** параметр компилятора, если указать **/Oxs**, сочетающий **/ox** параметр компилятора с [/Os (приоритет малая Код)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md). Объединенные параметры предпочитать размер кода.

Чтобы применить все доступные оптимизации уровня файла для сборки выпуска, рекомендуется указать [/O2 (максимизировать скорость)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) вместо **/ox**, и [/O1 (минимизировать размер)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) вместо из **/Oxs**. Еще больше оптимизации в версии сборки, учитывать [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md) параметр компилятора и [/LTCG (Создание кода во время компоновки)](../../build/reference/ltcg-link-time-code-generation.md) компоновщика.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. В разделе **свойства конфигурации**откройте **C/C++** и выберите **оптимизации** страницу свойств.

1. Изменить **оптимизации** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>См. также

[Параметры /O (оптимизация кода)](../../build/reference/o-options-optimize-code.md)  
[Параметры компилятора](../../build/reference/compiler-options.md)  
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)