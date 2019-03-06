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
ms.openlocfilehash: 6c3d3b51691247ddef5614cae113ffa9ded576e9
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57425241"
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

**/Cgthreads** параметр указывает максимальное число потоков cl.exe использует в параллельном режиме для оптимизации и кода на этапы создания компиляции. Обратите внимание на то, что не может быть пробела между **/cgthreads** и `number` аргумент. По умолчанию cl.exe использует четыре потока, как если бы **/cgthreads4** были указаны. Если доступно больше ядер процессора, увеличение значения `number` может ускорить сборку. Этот параметр особенно полезен, когда он объединяется с [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md).

Для сборки можно указать несколько уровней параллелизма. Параметр msbuild.exe **/maxcpucount** указывает число процессов MSBuild, которые могут выполняться параллельно. [/MP (построить с несколькими процессами)](../../build/reference/mp-build-with-multiple-processes.md) флаг компилятора указывает число процессов cl.exe, которые одновременно компилируют исходные файлы. **/Cgthreads** определяет число потоков, используемых каждым процессом cl.exe. Так как число потоков, одновременно выполняемых процессором, не может превышать число ядер процессора, указывать более высокие значения для всех этих параметров бессмысленно. Более того, это может иметь обратный эффект. Дополнительные сведения о построении проектов в параллельном режиме, см. в разделе [параллельное построение нескольких проектов](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации**, **C/C++** папки.

1. Выберите **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** свойство **/cgthreads**`N`, где `N` представляет собой значение от 1 до 8, а затем выберите **ОК**.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
