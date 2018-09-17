---
title: -Yc (создать предкомпилированный заголовочный файл) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- devlang-cpp
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.UsePrecompiledHeader
- /yc
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderThrough
- VC.Project.VCCLWCECompilerTool.UsePrecompiledHeader
- VC.Project.VCCLCompilerTool.PrecompiledHeaderThrough
dev_langs:
- C++
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- .pch files, creating
- -Yc compiler option [C++]
- /Yc compiler option [C++]
- Yc compiler option [C++]
ms.assetid: 47c2e555-b4f5-46e6-906e-ab5cf21f0678
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5288e748956a405073697ddd7331a73b95d8650
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714250"
---
# <a name="yc-create-precompiled-header-file"></a>/Yc (создать предкомпилированный заголовочный файл)

Предписывает компилятору создать файл предкомпилированного заголовка (PCH), представляющий состояние компиляции в определенной точке.

## <a name="syntax"></a>Синтаксис

> __/Yc__
>  __/Yc__*имя файла*

## <a name="arguments"></a>Аргументы

*filename*<br/>
Указывает на файл заголовка (.h). Если этот аргумент используется, компилятор компилирует весь код, включая h-файл.

## <a name="remarks"></a>Примечания

Когда **/Yc** указан без аргумента, компилятор компилирует весь код до конца базового исходного файла или до точки в базовом файле где [hdrstop](../../preprocessor/hdrstop.md) указана директива. Итоговый PCH-файл имеет такое же базовое имя как базовый исходный файл, если не указано имя другой файл с помощью **hdrstop** директивы pragma или **/FP** параметр.

Предварительно скомпилированный код сохраняется в файле с именем, созданным из базового имени файла, указанного с помощью **/Yc** расширением .pch и параметр. Можно также использовать [/Fp (имя. PCH-файл)](../../build/reference/fp-name-dot-pch-file.md) параметр, чтобы указать имя файла предкомпилированного заголовка.

Если вы используете __/Yc__*filename*, компилятор компилирует весь код, включая указанный файл для последующего использования с [/Yu (использование файла предкомпилированного заголовка)](../../build/reference/yu-use-precompiled-header-file.md) параметр.

Если параметры __/Yc__*filename* и __/Yu__*filename* возникают в одной командной строке и ссылки, или оба подразумевают, то же имя файла __/Yc__*filename* имеет более высокий приоритет. Эта функция упрощает создание файлов makefile.

Дополнительные сведения о предкомпилированных заголовках см. в разделе:

- [/Y (предкомпилированные заголовки)](../../build/reference/y-precompiled-headers.md)

- [Создание предварительно скомпилированных файлов заголовков](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Выберите файл cpp. CPP-файл должен #include в h-файл, содержащий сведения о предкомпилированных заголовках. Проекта **/Yc** параметр можно переопределить на уровне файлов.

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте **свойства конфигурации**, **C/C++**, **предкомпилированные заголовки** страницу свойств.

1. Изменить **предкомпилированный заголовок** свойство.

1. Чтобы задать имя файла, изменение **файла предкомпилированного заголовка** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. разделы <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>.

## <a name="example"></a>Пример

Рассмотрим следующий код.

```cpp
// prog.cpp
// compile with: cl /c /Ycmyapp.h prog.cpp
#include <afxwin.h>   // Include header for class library
#include "resource.h" // Include resource definitions
#include "myapp.h"    // Include information specific to this app
// ...
```

При компиляции этого кода с помощью команды `CL /YcMYAPP.H PROG.CPP`, компилятор сохраняет всю предварительную обработку для AFXWIN.h, RESOURCE.h и MYAPP.h в файл предкомпилированного заголовка с именем MYAPP.pch.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[Создание предварительно скомпилированных файлов заголовков](../../build/reference/creating-precompiled-header-files.md)