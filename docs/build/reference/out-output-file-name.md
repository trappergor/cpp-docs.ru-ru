---
title: /OUT (имя выходного файла)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.OutputFile
- /out
helpviewer_keywords:
- output files, name linker option
- -OUT linker option
- OUT linker option
- /OUT C++ linker option
- linker [C++], output files
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
ms.openlocfilehash: 395a2475ec572476f80b17cc5ffab7c2724e6b02
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57418052"
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
