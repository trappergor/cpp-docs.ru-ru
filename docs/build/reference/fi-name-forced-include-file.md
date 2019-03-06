---
title: /FI (имя принудительно включаемого файла)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.ForcedIncludes
- VC.Project.VCCLCompilerTool.ForcedIncludeFiles
- VC.Project.VCCLWCECompilerTool.ForcedIncludeFiles
- /fi
helpviewer_keywords:
- FI compiler option [C++]
- -FI compiler option [C++]
- /FI compiler option [C++]
- preprocess header file compiler option [C++]
ms.assetid: 07e79577-8152-4df9-a64c-aae08c603397
ms.openlocfilehash: b91ca1ba6cc97157be0ab16fc18e065dc501d5fd
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422472"
---
# <a name="fi-name-forced-include-file"></a>/FI (имя принудительно включаемого файла)

Дает препроцессору указание для обработки указанного заголовка файла.

## <a name="syntax"></a>Синтаксис

```
/FI[ ]pathname
```

## <a name="remarks"></a>Примечания

Этот параметр действует так же как и при указании файла в двойные кавычки в `#include` директив в первой строке каждый исходный файл, заданный в командной строке, в переменной среды компилятора CL или в командный файл. При использовании нескольких **/FI** "Параметры", "файлы включены в порядке, они обрабатываются CL.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **Дополнительно** страницу свойств.

1. Изменить **принудительно включать** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles%2A>.

## <a name="see-also"></a>См. также

[Параметры выходного файла (/F)](../../build/reference/output-file-f-options.md)<br/>
[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[Указание пути](../../build/reference/specifying-the-pathname.md)
