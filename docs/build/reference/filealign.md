---
title: / FILEALIGN (выравнивание разделов в файлах) | Документы Microsoft
ms.date: 10/23/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /filealign
dev_langs:
- C++
helpviewer_keywords:
- linker align sections
- /FILEALIGN linker option
- -FILEALIGN linker option
- FILEALIGN linker option
ms.assetid: c1017a35-8d71-4ad9-934b-a3e3ea037fa0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c8a737801663a2c7c1e896166291a1635fbbe6c4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373274"
---
# <a name="filealign-align-sections-in-files"></a>/ FILEALIGN (выравнивание разделов в файлах)

**/Filealign** параметр компоновщика позволяет задать выравнивание разделов, которые записываются в выходной файл, кратными указанного размера.

## <a name="syntax"></a>Синтаксис

> __/ FILEALIGN:__*размер*

### <a name="parameters"></a>Параметры

*size*  
Размер раздела выравнивания в байтах, которую должно быть степенью двух.

## <a name="remarks"></a>Примечания

**/Filealign** предписывает компоновщику выравнивания каждого раздела в файле вывода на границе, кратной *размер* значение. По умолчанию компоновщик не использует размер фиксированной выравнивания.

**/Filealign** параметр можно использовать для повышения эффективности использования дискового пространства, а также чтобы сделать страницы загрузки с диска быстрее. Меньший размер раздела можно использовать для приложений, выполняющихся на небольших устройствах или сократить объем загружаемых файлов. Выравнивание разделов на диске не влияет на выравнивание в памяти.

Используйте [DUMPBIN](dumpbin-reference.md) для просмотра информации о разделах выходного файла.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **командной строки** на странице свойств в **компоновщика** папки.

1. Введите имя параметра **/filealign:** и размер в **Дополнительные параметры** поле.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
[Параметры компоновщика](../../build/reference/linker-options.md)