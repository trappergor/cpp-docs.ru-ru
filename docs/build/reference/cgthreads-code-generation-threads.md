---
title: /cgthreads (потоки создания кода)
ms.date: 07/31/2020
f1_keywords:
- /cgthreads
helpviewer_keywords:
- /cgthreads compiler option (C++)
- -cgthreads compiler option (C++)
- cgthreads compiler option (C++)
- cgthreads
ms.assetid: 64bc768c-6caa-4baf-9dea-7cfa1ffb01c2
ms.openlocfilehash: 319a42ab68f02df6019ff283f1039ef3d561c4a0
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520879"
---
# <a name="cgthreads-code-generation-threads"></a>`/cgthreads`(Потоки создания кода)

Задает число потоков cl.exe, используемых для оптимизации и создания кода.

## <a name="syntax"></a>Синтаксис

> **`/cgthreads1`**\
> **`/cgthreads2`**\
> **`/cgthreads3`**\
> **`/cgthreads4`**\
> **`/cgthreads5`**\
> **`/cgthreads6`**\
> **`/cgthreads7`**\
> **`/cgthreads8`**

## <a name="arguments"></a>Аргументы

**`cgthreadsN`**\
Максимальное число потоков для использования cl.exe, где *N* — число в диапазоне от 1 до 8.

## <a name="remarks"></a>Примечания

**`cgthreads`** Параметр указывает максимальное число потоков, которые cl.exe параллельно используются для этапов оптимизации и создания кода компиляции. Обратите внимание, что между **`cgthreads`** и аргументом *Number* не может быть пробела. По умолчанию cl.exe использует четыре потока, как если **`/cgthreads4`** бы были указаны. Если доступно больше ядер процессора, то значение большего *числа* может увеличить время сборки. Этот параметр особенно полезен при объединении с [ `/GL` (оптимизация всей программы)](gl-whole-program-optimization.md).

Для сборки можно указать несколько уровней параллелизма. Параметр msbuild.exe **`/maxcpucount`** указывает количество процессов MSBuild, которые могут выполняться параллельно. Флаг компилятора [ `/MP` (сборка с несколькими процессами)](mp-build-with-multiple-processes.md) указывает количество процессов cl.exe, одновременно выполняющих компиляцию исходных файлов. **`cgthreads`** Параметр определяет количество потоков, используемых каждым процессом cl.exe. Процессор может выполнять столько потоков одновременно, что и процессорные ядра. Нецелесообразно указывать большие значения для всех этих параметров одновременно, и это может быть понизит производительность. Дополнительные сведения о параллельной сборке проектов см. [в разделе параллельное построение нескольких проектов](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **Свойства конфигурации**  >  **C/C++**  >  **Командная строка** .

1. Измените свойство **Дополнительные параметры** , чтобы включить **`cgthreadsN`** , где *`N`* — значение от 1 до 8, а затем нажмите кнопку **ОК**.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора КОМПИЛЯТОРОМ MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
