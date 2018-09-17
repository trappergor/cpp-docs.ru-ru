---
title: -OUT (имя выходного файла) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.OutputFile
- /out
dev_langs:
- C++
helpviewer_keywords:
- output files, name linker option
- -OUT linker option
- OUT linker option
- /OUT C++ linker option
- linker [C++], output files
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c4bfc79a257424820bed5f784cb0a83daf016d5
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725404"
---
# <a name="out-output-file-name"></a>/OUT (имя выходного файла)

```
/OUT:filename
```

## <a name="arguments"></a>Аргументы

*filename*<br/>
Определяемое пользователем имя для выходного файла. Он заменяет имя по умолчанию.

## <a name="remarks"></a>Примечания

Параметр / OUT переопределяет стандартное имя и расположение программы, которую создает компоновщик.

По умолчанию компоновщик формирует имя файла, используя базовое имя первого указанного файла OBJ и соответствующего расширения (.exe или .dll).

Этот параметр по умолчанию базовое имя для сопоставления MAPFILE или импорта библиотеки. Дополнительные сведения см. в разделе [Создание файла сопоставления](../../build/reference/map-generate-mapfile.md) (/ MAP) и [/IMPLIB](../../build/reference/implib-name-import-library.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **Общие** страницу свойств.

1. Изменить **выходной файл** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)