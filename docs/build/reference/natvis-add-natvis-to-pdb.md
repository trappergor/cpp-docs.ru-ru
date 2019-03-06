---
title: / NATVIS (Добавление файла Natvis в PDB-ФАЙЛ)
ms.date: 08/10/2017
f1_keywords:
- /natvis
- VC.Project.VCLinkerTool.ImportLIbrary
helpviewer_keywords:
- NATVIS linker option
- /NATVIS linker option
- -NATVIS linker option
- Add Natvis file to PDB
ms.assetid: 8747fc0c-701a-4796-bb4d-818ab4465cca
ms.openlocfilehash: 983cbe4c4bd4164d81b83a23fe19569318d5193c
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424981"
---
# <a name="natvis-add-natvis-to-pdb"></a>/ NATVIS (Добавление файла Natvis в PDB-ФАЙЛ)

> / NATVIS:*имя файла*

## <a name="parameters"></a>Параметры

*filename*<br/>
Natvis-файл для добавления в PDB-файл. Он внедряет визуализация отладчика в файле Natvis в PDB-ФАЙЛ.

## <a name="remarks"></a>Примечания

Параметр /NATVIS внедряет визуализация отладчика, определенный в natvis-файла *filename* в PDB-файл, созданный с помощью LINK. Это позволяет отладчику отображать визуализации, независимо от natvis-файл. Можно использовать несколько вариантов /NATVIS для внедрения более одного файла Natvis в файл PDB.

LINK игнорирует /NATVIS, когда PDB-файл не создается с помощью [/DEBUG](../../build/reference/debug-generate-debug-info.md) параметр. Сведения о создании и использовании natvis-файлы, см. в разделе [Создание настраиваемых представлений собственных объектов в отладчике Visual Studio](/visualstudio/debugger/create-custom-views-of-native-objects).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Выберите **командной строки** страницы свойств в **компоновщика** папки.

1. Добавьте параметр /NATVIS **Дополнительные параметры** текстовое поле.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- Этот параметр не поддерживает программный эквивалент.

## <a name="see-also"></a>См. также

[Создание настраиваемых представлений собственных объектов в отладчике Visual Studio](/visualstudio/debugger/create-custom-views-of-native-objects)<br/>
[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
