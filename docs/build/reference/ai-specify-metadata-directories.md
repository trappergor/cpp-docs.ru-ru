---
title: -AI (указание каталогов метаданных) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.AdditionalUsingDirectories
- VC.Project.VCNMakeTool.AssemblySearchPath
- /AI
- VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories
dev_langs:
- C++
helpviewer_keywords:
- /AI compiler option [C++]
- AI compiler option [C++]
- -AI compiler option [C++]
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 985ff4eb96b904dc9c5b4377b336109b00e06b40
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716596"
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

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

2. Выберите **свойства конфигурации** > **C/C++** > **Общие** страницу свойств.

3. Изменить **дополнительные #using каталогов** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[Директива #using](../../preprocessor/hash-using-directive-cpp.md)