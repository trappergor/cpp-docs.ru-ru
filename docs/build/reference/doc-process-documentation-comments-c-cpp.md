---
title: /doc (обработка комментариев документации) (C/C++)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- /doc
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
helpviewer_keywords:
- /doc compiler option [C++]
- comments, C++ code
- XML documentation, comments in source files
- -doc compiler option [C++]
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
ms.openlocfilehash: 90f63a972245114424b64d4131420dcb4e1e925a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809799"
---
# <a name="doc-process-documentation-comments-cc"></a>/doc (обработка комментариев документации) (C/C++)

Указывает компилятору обработка комментариев документации в файлах исходного кода и создания XDC-файл для каждого файла исходного кода, имеющий комментарии к документации.

## <a name="syntax"></a>Синтаксис

> **/ doc**[*имя*]

## <a name="arguments"></a>Аргументы

*name*<br/>
Имя, компилятор создает XDC-файла. Действительно только при передаче CPP-файл в компиляцию.

## <a name="remarks"></a>Примечания

XDC-файлы обрабатываются в XML-файл с xdcmake.exe. Дополнительные сведения см. в разделе [Справочник по XDCMake](xdcmake-reference.md).

Можно добавить комментарии к документации для файлов исходного кода. Дополнительные сведения см. в разделе [Рекомендуемые теги для комментариев документации](recommended-tags-for-documentation-comments-visual-cpp.md).

Чтобы использовать созданный XML-файл с поддержкой технологии IntelliSense, сделайте имя файла XML-файла, так же, как сборка, вам требуется поддерживать, а сам XML-файл находится в том же каталоге, что и сборка. При ссылке на сборку в проект Visual Studio, также находится XML-файл. Дополнительные сведения см. в разделе [использование технологии IntelliSense](/visualstudio/ide/using-intellisense) и [Создание примечаний к коду XML](/visualstudio/ide/supplying-xml-code-comments).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **выходные файлы** страницу свойств.

1. Изменить **создавать файлы XML-документации** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
