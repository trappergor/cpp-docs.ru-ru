---
title: /cgthreads (потоки создания кода)
ms.date: 11/04/2016
f1_keywords:
- /cgthreads
helpviewer_keywords:
- /cgthreads compiler option (C++)
- -cgthreads compiler option (C++)
- cgthreads compiler option (C++)
- cgthreads
ms.assetid: 64bc768c-6caa-4baf-9dea-7cfa1ffb01c2
ms.openlocfilehash: df353eb255c731478863ed6088cafa1cc38053fb
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807433"
---
# <a name="cgthreads-code-generation-threads"></a>/cgthreads (потоки создания кода)

Задает число потоков cl.exe, используемых для оптимизации и создания кода.

## <a name="syntax"></a>Синтаксис

```
/cgthreads[1-8]
```

## <a name="arguments"></a>Аргументы

*номер*<br/>
Максимальное число потоков, используемых cl.exe, — в диапазоне от 1 до 8.

## <a name="remarks"></a>Примечания

**/Cgthreads** параметр указывает максимальное число потоков cl.exe использует в параллельном режиме для оптимизации и кода на этапы создания компиляции. Обратите внимание на то, что не может быть пробела между **/cgthreads** и `number` аргумент. По умолчанию cl.exe использует четыре потока, как если бы **/cgthreads4** были указаны. Если доступно больше ядер процессора, увеличение значения `number` может ускорить сборку. Этот параметр особенно полезен, когда он объединяется с [/GL (оптимизация всей программы)](gl-whole-program-optimization.md).

Для сборки можно указать несколько уровней параллелизма. Параметр msbuild.exe **/maxcpucount** указывает число процессов MSBuild, которые могут выполняться параллельно. [/MP (построить с несколькими процессами)](mp-build-with-multiple-processes.md) флаг компилятора указывает число процессов cl.exe, которые одновременно компилируют исходные файлы. **/Cgthreads** определяет число потоков, используемых каждым процессом cl.exe. Так как число потоков, одновременно выполняемых процессором, не может превышать число ядер процессора, указывать более высокие значения для всех этих параметров бессмысленно. Более того, это может иметь обратный эффект. Дополнительные сведения о построении проектов в параллельном режиме, см. в разделе [параллельное построение нескольких проектов](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации**, **C/C++** папки.

1. Выберите **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** свойство **/cgthreads**`N`, где `N` представляет собой значение от 1 до 8, а затем выберите **ОК**.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
