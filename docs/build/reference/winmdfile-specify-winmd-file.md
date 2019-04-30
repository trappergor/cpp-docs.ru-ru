---
title: /WINMDFILE (укажите файл winmd)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
ms.openlocfilehash: 5d24d1d1aad8442f549dcb1aa4bd6414070c282c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316487"
---
# <a name="winmdfile-specify-winmd-file"></a>/WINMDFILE (укажите файл winmd)

Задает имя файла для выходного файла метаданных среды выполнения Windows (.winmd), созданного [/WINMD](winmd-generate-windows-metadata.md) параметр компоновщика.

```
/WINMDFILE:filename
```

## <a name="remarks"></a>Примечания

Используйте значение, которое указано в `filename` для переопределения используемого по умолчанию имя файла .winmd (`binaryname`.winmd). Обратите внимание на то, что вы не добавляете «.winmd» `filename`.  Если несколько значений в списке на **/WINMDFILE** командной строки, последний имеет приоритет.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **компоновщика** папки.

1. Выберите **метаданных Windows** страницу свойств.

1. В **файл метаданных Windows** введите нужный файл.

## <a name="see-also"></a>См. также

[/WINMD (создание метаданных Windows)](winmd-generate-windows-metadata.md)<br/>
[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
