---
title: -DRIVER (драйвер режима ядра Windows NT) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.driver
- /driver
dev_langs:
- C++
helpviewer_keywords:
- kernel mode driver
- -DRIVER linker option
- DRIVER linker option
- /DRIVER linker option
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66291391ed38c27ce7446eccc6fca227c7c2c2d7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373118"
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER (драйвер режима ядра Windows NT)

>ИЛИ ДРАЙВЕР [: UPONLY |: WDM]

## <a name="remarks"></a>Примечания

Используйте **/Driver** компоновщика для построения драйвер режима ядра Windows NT.

**/DRIVER:UPONLY** указывает компоновщику добавить **IMAGE_FILE_UP_SYSTEM_ONLY** бит в характеристики в выходном заголовке, чтобы указать, что это однопроцессорный (UP) драйвер. Операционная система отклонит загрузку UP-драйвера в многопроцессорной (MP) системе.

**/DRIVER:WDM** указывает компоновщику задать **бита параметра** бит в поле DllCharacteristics необязательного заголовка.

Если **/Driver** не указан, эти битовые флаги не устанавливаются компоновщиком.

Если **/Driver** указано:

- **/ Fixed: no** действует. Дополнительные сведения см. в разделе [Параметр /FIXED (фиксированный базовый адрес)](../../build/reference/fixed-fixed-base-address.md).

- Расширение выходного файла задано значение .sys. Используйте **/OUT** Чтобы изменить имя файла по умолчанию и расширение. Дополнительные сведения см. в разделе [Параметр /OUT (имя выходного файла)](../../build/reference/out-output-file-name.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **системы** страницу свойств.

1. Изменить **драйвер** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- В разделе [VCLinkerTool.driver свойства](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver?view=visualstudiosdk-2017#Microsoft_VisualStudio_VCProjectEngine_VCLinkerTool_driver).

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
[Параметры компоновщика](../../build/reference/linker-options.md)
