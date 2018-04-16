---
title: -DRIVER (драйвер режима ядра Windows NT) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 29234e3c0e368c7710f9071c753422bc4e6ef2b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
