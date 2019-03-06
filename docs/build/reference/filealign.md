---
title: / FILEALIGN (выравнивание разделов в файлах)
ms.date: 10/23/2017
f1_keywords:
- /filealign
helpviewer_keywords:
- linker align sections
- /FILEALIGN linker option
- -FILEALIGN linker option
- FILEALIGN linker option
ms.assetid: c1017a35-8d71-4ad9-934b-a3e3ea037fa0
ms.openlocfilehash: f2f46796a939d068c893e397499a42fe0bf6f41a
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417974"
---
# <a name="filealign-align-sections-in-files"></a>/ FILEALIGN (выравнивание разделов в файлах)

**/Filealign** параметр компоновщика позволяет задать выравнивание разделов, записываемый в выходной файл кратными указанного размера.

## <a name="syntax"></a>Синтаксис

> __/ FILEALIGN:__*размер*

### <a name="parameters"></a>Параметры

*size*<br/>
Размер выравнивания раздела в байтах, которую должно быть степенью двух.

## <a name="remarks"></a>Примечания

**/Filealign** предписывает компоновщику выравнивание каждого раздела в выходной файл на границе, кратной *размер* значение. По умолчанию компоновщик не использует выравнивание фиксированный размер.

**/Filealign** параметр может использоваться для повышения эффективности использования дискового пространства или сделать страницу загружает с диска быстрее. Меньший размер раздела может быть полезно для приложений, работающих на небольших устройствах или сократить объем скачиваемых файлов. Выравнивание разделов на диске не влияет на выравнивание в памяти.

Используйте [DUMPBIN](dumpbin-reference.md) для просмотра информации о разделах выходного файла.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **командной строки** страницы свойств в **компоновщика** папки.

1. Введите имя параметра **/filealign:** и размер в **Дополнительные параметры** поле.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
