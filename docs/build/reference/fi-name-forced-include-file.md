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
ms.openlocfilehash: e047ecc5266a898f2c6dc24be3c204f8ddf94386
ms.sourcegitcommit: 90817d9d78fbaed8ffacde63f3add334842e596f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/20/2019
ms.locfileid: "58278376"
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

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **Дополнительно** страницу свойств.

1. Изменить **принудительно включаемого файла** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles%2A>.

## <a name="see-also"></a>См. также

[Параметры выходного файла (/F)](output-file-f-options.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[Указание пути](specifying-the-pathname.md)
