---
title: /DEF (указание файла определения модуля)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ModuleDefinitionFile
- /def
helpviewer_keywords:
- module definition files, specifying
- DEF linker option
- -DEF linker option
- module definition files
- /DEF linker option
ms.assetid: 6497fa68-65f0-48ca-8f66-b87166fc631a
ms.openlocfilehash: c08412fb50835485e7941b2bb1db088943387b71
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272312"
---
# <a name="def-specify-module-definition-file"></a>/DEF (указание файла определения модуля)

```
/DEF:filename
```

## <a name="arguments"></a>Аргументы

*filename*<br/>
Имя файла определения модуля (.def) для передачи в компоновщик.

## <a name="remarks"></a>Примечания

Параметр/DEF передает файл определения модуля (.def) в компоновщик. Ссылку можно указать только один DEF-файл. Дополнительные сведения о DEF-файлы, см. в разделе [файлы определения модуля](module-definition-dot-def-files.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **ввода** страницу свойств.

1. Изменить **файл определения модуля** свойство.

Чтобы указать DEF-файл в среде разработки, следует добавить его в проект, а также другие файлы и затем укажите файл, чтобы параметр/DEF.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
