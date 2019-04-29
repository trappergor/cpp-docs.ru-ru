---
title: /AI (указание каталогов метаданных)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.AdditionalUsingDirectories
- VC.Project.VCNMakeTool.AssemblySearchPath
- /AI
- VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories
helpviewer_keywords:
- /AI compiler option [C++]
- AI compiler option [C++]
- -AI compiler option [C++]
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
ms.openlocfilehash: 3633cfe34a4f9c627f84cf401cb559f02f8c8229
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273226"
---
# <a name="ai-specify-metadata-directories"></a>/AI (указание каталогов метаданных)

Указывает каталог, в котором компилятор будет производить поиск для разрешения ссылок, переданных в директиву `#using`.

## <a name="syntax"></a>Синтаксис

> **/AI**_каталога_

## <a name="arguments"></a>Аргументы

*Каталог*<br/>
Каталог или путь, по которому компилятор будет выполнять поиск.

## <a name="remarks"></a>Примечания

Можно передать только один каталог **/AI** вызова. Укажите один **/AI** параметр для каждого пути, необходимо выполнить поиск. Например, чтобы добавить в путь поиска компилятора для C:\Project\Meta и C:\Common\Meta `#using` добавьте директивы, `/AI"C:\Project\Meta" /AI"C:\Common\Meta"` в командную строку компилятора или добавьте каждый каталог в **дополнительные #using каталогов** свойство в Visual Studio.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **Общие** страницу свойств.

1. Изменить **дополнительные #using каталогов** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[Директива #using](../../preprocessor/hash-using-directive-cpp.md)
