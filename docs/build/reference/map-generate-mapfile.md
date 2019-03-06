---
title: /MAP (создание файла сопоставления)
ms.date: 11/04/2016
f1_keywords:
- /map
- VC.Project.VCLinkerTool.MapFileName
- VC.Project.VCLinkerTool.GenerateMapFile
helpviewer_keywords:
- mapfiles, creating linker
- generate mapfile linker option
- mapfile linker option
- mapfiles, information about program being linked
- MAP linker option
- -MAP linker option
- mapfiles, specifying file name
- /MAP linker option
ms.assetid: 9ccce53d-4e36-43da-87b0-7603ddfdea63
ms.openlocfilehash: 769fdc6a3980be34d92fc722099fde11ab677dc8
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417896"
---
# <a name="map-generate-mapfile"></a>/MAP (создание файла сопоставления)

```
/MAP[:filename]
```

## <a name="arguments"></a>Аргументы

*filename*<br/>
Определяемое пользователем имя файла сопоставления. Он заменяет имя по умолчанию.

## <a name="remarks"></a>Примечания

Параметр/MAP предписывает компоновщику Создание файла сопоставления.

По умолчанию компоновщик дает файлу сопоставления базовое имя программы и расширение MAP. Необязательный *filename* позволяет переопределить имя по умолчанию для файла сопоставления.

Файл сопоставления — это текстовый файл, содержащий следующие сведения о компонующейся программе:

- Имя модуля, который является базовым именем файла

- Метка времени из заголовка файла программы (не из файловой системы)

- Список групп в программе с каждой группы начальный адрес (как *разделе*:*смещение*), длина имени группы и класса

- Список открытых символов, с использованием всех адресов (как *разделе*:*смещение*), символ имя неструктурированного адреса и OBJ-файле, где определен символ

- Точка входа (как *разделе*:*смещение*)

[/MAPINFO предписывает](../../build/reference/mapinfo-include-information-in-mapfile.md) указывает Дополнительные сведения, включаемые в файл сопоставления.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **Отладка** страницу свойств.

1. Изменить **Создание файла сопоставления** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. разделы <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
