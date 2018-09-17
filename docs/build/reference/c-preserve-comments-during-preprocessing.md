---
title: -C (сохранять комментарии во время предварительной обработки) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.KeepComments
- /c
- VC.Project.VCCLWCECompilerTool.KeepComments
dev_langs:
- C++
helpviewer_keywords:
- comments, not stripping during preprocessing
- preserve comments during preprocessing
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 20973969385d0b5c61872a12f4d0168420bc2eef
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713189"
---
# <a name="c-preserve-comments-during-preprocessing"></a>/C (сохранять комментарии во время предварительной обработки)

Сохраняет комментарии на этапе предварительной обработки.

## <a name="syntax"></a>Синтаксис

```
/C
```

## <a name="remarks"></a>Примечания

Этот параметр компилятора требует **/E**, **/P**, или **/EP** параметр.

В следующем образце кода будет отображать комментарии исходного кода.

```
// C_compiler_option.cpp
// compile with: /E /C /c
int i;   // a variable
```

В этом примере создаст следующие выходные данные.

```
#line 1 "C_compiler_option.cpp"
int i;   // a variable
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **препроцессор** страницу свойств.

1. Изменить **оставлять комментарии** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[/E (Предварительная обработка до stdout)](../../build/reference/e-preprocess-to-stdout.md)
[/P (Предварительная обработка в файл)](../../build/reference/p-preprocess-to-a-file.md)
[/EP (Предварительная обработка в stdout без директив #line)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)