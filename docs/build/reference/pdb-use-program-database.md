---
title: /PDB (Использование базы данных программы)
ms.date: 11/04/2016
f1_keywords:
- /pdb
- VC.Project.VCLinkerTool.ProgramDatabaseFile
helpviewer_keywords:
- -PDB linker option
- /PDB linker option
- PDB linker option
- PDB files, creating
- .pdb files, creating
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
ms.openlocfilehash: c7d3b571a429d780c0c5eea0ad498499c615245f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589553"
---
# <a name="pdb-use-program-database"></a>/PDB (Использование базы данных программы)

```
/PDB:filename
```

## <a name="arguments"></a>Аргументы

*filename*<br/>
Определяемое пользователем имя для базы данных программы (PDB), которую создает компоновщик. Он заменяет имя по умолчанию.

## <a name="remarks"></a>Примечания

По умолчанию когда [/DEBUG](../../build/reference/debug-generate-debug-info.md) указан, компоновщик создает базу данных программы (PDB), содержащий отладочную информацию. Имя файла по умолчанию для PDB-ФАЙЛ имеет базовое имя программы и расширение .pdb.

Используйте/PDB:*filename* для указания имени PDB-файла. Если не задан параметр/debug, параметр/PDB учитывается.

PDB-файл может быть до 2 ГБ.

Дополнительные сведения см. в разделе [PDB-файлы в качестве входных данных компоновщика](../../build/reference/dot-pdb-files-as-linker-input.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **Отладка** страницу свойств.

1. Изменить **создавать файл базы данных программы** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)