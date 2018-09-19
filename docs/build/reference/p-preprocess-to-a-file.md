---
title: -P (вывод результатов предварительной обработки файла) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFile
- /p
- VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile
dev_langs:
- C++
helpviewer_keywords:
- /P compiler option [C++]
- -P compiler option [C++]
- P compiler option [C++]
- output files, preprocessor
- preprocessing output files
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4cbec53526fe90d1b4644b5b9fdd667d0fffcbe8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714510"
---
# <a name="p-preprocess-to-a-file"></a>/P (вывод результатов предварительной обработки в файл)

Предварительно обрабатывает исходные файлы C и C++ и записывает предварительно обработанные выходные данные в файл.

## <a name="syntax"></a>Синтаксис

```
/P
```

## <a name="remarks"></a>Примечания

Файл имеет такое же базовое имя исходного файла и расширение i. В процессе выполняются все директивы препроцессора, расширения макросов и комментарии будут удалены. Чтобы сохранить комментарии в предварительно обработанные выходные данные, используйте [/C (сохранять комментарии во время предварительной обработки)](../../build/reference/c-preserve-comments-during-preprocessing.md) вместе с параметром **/P**.

**/P** добавляет `#line` директивы в выходные данные, в начале и конце каждого включенного файла, а также вокруг строк, удаленных директивами препроцессора для условной компиляции. Эти директивы перенумерации строки из предварительно обработанного файла. В результате ошибки, созданные в более поздних этапах обработки см. для номера строки исходного файла, а не строк предварительно обработанного файла. Чтобы подавить формирование `#line` использовать директивы, [/EP (Предварительная обработка в stdout без директив #line)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) производительны **/P**.

**/P** параметр отменяет компиляцию. Он не создает OBJ-файл, даже если вы используете [/Fo (имя объектного файла)](../../build/reference/fo-object-file-name.md). Отправьте предварительно обработанного файла для компиляции. **/P** также подавляются выходные файлы из **/FA**, **/Fa**, и **/Fm** параметры. Дополнительные сведения см. в разделе [/FA, /Fa (файл листинга)](../../build/reference/fa-fa-listing-file.md) и [/Fm (имя файла сопоставления)](../../build/reference/fm-name-mapfile.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **препроцессор** страницу свойств.

1. Изменить **Создание предварительно обработанного файла** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.

## <a name="example"></a>Пример

Следующая командная строка выполняет предварительную обработку `ADD.C`, сохраняет комментарии, добавляет `#line` директивы и записывает результат в файл `ADD.I`:

```
CL /P /C ADD.C
```

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[/Fi (предварительная обработка имени выходного файла)](../../build/reference/fi-preprocess-output-file-name.md)