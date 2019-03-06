---
title: /PDBSTRIPPED (удалить закрытые символы)
ms.date: 11/04/2016
f1_keywords:
- /pdbstripped
- VC.Project.VCLinkerTool.StripPrivateSymbols
helpviewer_keywords:
- /PDBSTRIPPED linker option
- -PDBSTRIPPED linker option
- .pdb files, stripping private symbols
- PDB files, stripping private symbols
- PDBSTRIPPED linker option
ms.assetid: 9b9e0070-6a13-4142-8180-19c003fbbd55
ms.openlocfilehash: c0a79eb8d1c00be2b855ec08ffe44f4e7d7a2e05
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57412631"
---
# <a name="pdbstripped-strip-private-symbols"></a>/PDBSTRIPPED (удалить закрытые символы)

```
/PDBSTRIPPED:pdb_file_name
```

## <a name="arguments"></a>Аргументы

*pdb_file_name*<br/>
Определяемое пользователем имя для базы данных программы (PDB), которую создает компоновщик.

## <a name="remarks"></a>Примечания

Параметр/PDBSTRIPPED создает второй файл базы данных (PDB) программы при построении образа программы с любыми параметрами компилятора или компоновщика, создающими файл PDB ([/DEBUG](../../build/reference/debug-generate-debug-info.md), [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), /Zd или /Zi). Второй PDB-файл не содержит символов, которые нежелательно передавать клиентам. Второй PDB-файл будет содержать только:

- Открытые символы

- Список объектных файлов и частей исполняемого файла, к которым они относятся

- Записи оптимизации указателя фрейма (FPO) отладки используется для прохода по стеку

Очищенный PDB-файл не будет содержать:

- Сведения о типе

- Информация о номере строки

- На объект файла CodeView символы, например, для функций, локальных переменных и статических данных

Полный PDB-файл будет создаваться при использовании/PDBSTRIPPED.

Если вы не создали PDB-файл, / PDBSTRIPPED учитывается.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **Отладка** страницу свойств.

1. Изменить **удалить закрытые символы** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
