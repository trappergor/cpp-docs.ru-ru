---
title: /CGTHREADS (потоки компилятора)
ms.date: 11/04/2016
helpviewer_keywords:
- /CGTHREADS linker option
- -CGTHREADS linker option
- CGTHREADS linker option
ms.assetid: 4b52cfdb-3702-470b-9580-fabeb1417488
ms.openlocfilehash: b778802d3fffcaafc0cf01ac46ae85c4efbef95c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294672"
---
# <a name="cgthreads-compiler-threads"></a>/CGTHREADS (потоки компилятора)

Задает число потоков cl.exe, используемых для оптимизации и создания кода, если задано создание кода во время компоновки.

## <a name="syntax"></a>Синтаксис

```
/CGTHREADS:[1-8]
```

## <a name="arguments"></a>Аргументы

*номер*<br/>
Максимальное число потоков, используемых cl.exe, — в диапазоне от 1 до 8.

## <a name="remarks"></a>Примечания

**/Cgthreads** параметр указывает максимальное число потоков cl.exe использует параллельно на этапах оптимизации и создания кода при во время компиляции, если создание кода ([/LTCG](ltcg-link-time-code-generation.md)) — указан. По умолчанию cl.exe использует четыре потока, как если бы **/CGTHREADS:4** были указаны. Если доступно больше ядер процессора, увеличение значения `number` может ускорить сборку.

Для сборки можно указать несколько уровней параллелизма. Параметр msbuild.exe **/maxcpucount** указывает число процессов MSBuild, которые могут выполняться параллельно. [/MP (построить с несколькими процессами)](mp-build-with-multiple-processes.md) флаг компилятора указывает число процессов cl.exe, которые одновременно компилируют исходные файлы. [/Cgthreads](cgthreads-code-generation-threads.md) компилятор определяет число потоков, используемых каждым процессом cl.exe. Так как число потоков, одновременно выполняемых процессором, не может превышать число ядер процессора, указывать более высокие значения для всех этих параметров бессмысленно. Более того, это может иметь обратный эффект. Дополнительные сведения о построении проектов в параллельном режиме, см. в разделе [параллельное построение нескольких проектов](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации**, **компоновщика** папки.

1. Выберите **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** свойство **/cgthreads:**`number`, где `number` представляет собой значение от 1 до 8, а затем выберите **ОК**.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компоновщика MSVC](linker-options.md)<br/>
[Справочник по компоновщику MSVC](linking.md)
