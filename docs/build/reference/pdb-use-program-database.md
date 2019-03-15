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
ms.openlocfilehash: ddcf83cafd5f499158f3116f04e40397b7f8d0a8
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821512"
---
# <a name="pdb-use-program-database"></a>/PDB (Использование базы данных программы)

```
/PDB:filename
```

## <a name="arguments"></a>Аргументы

*filename*<br/>
Определяемое пользователем имя для базы данных программы (PDB), которую создает компоновщик. Он заменяет имя по умолчанию.

## <a name="remarks"></a>Примечания

По умолчанию когда [/DEBUG](debug-generate-debug-info.md) указан, компоновщик создает базу данных программы (PDB), содержащий отладочную информацию. Имя файла по умолчанию для PDB-ФАЙЛ имеет базовое имя программы и расширение .pdb.

Используйте/PDB:*filename* для указания имени PDB-файла. Если не задан параметр/debug, параметр/PDB учитывается.

PDB-файл может быть до 2 ГБ.

Дополнительные сведения см. в разделе [PDB-файлы в качестве входных данных компоновщика](dot-pdb-files-as-linker-input.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **Отладка** страницу свойств.

1. Изменить **создавать файл базы данных программы** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>.

## <a name="see-also"></a>См. также

[Справочник по MSVC компоновщика](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
