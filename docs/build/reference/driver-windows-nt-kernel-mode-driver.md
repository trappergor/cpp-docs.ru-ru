---
title: -DRIVER (драйвер режима ядра Windows NT) | Документация Майкрософт
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
ms.openlocfilehash: 8ae096c502cdc94d47a516caf4c29ac4f3eceb4b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705553"
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER (драйвер режима ядра Windows NT)

>/ DRIVER [: UPONLY |: WDM]

## <a name="remarks"></a>Примечания

Используйте **/Driver** параметр компоновщика для сборки драйвера режима ядра Windows NT.

**/DRIVER:UPONLY** указывает компоновщику добавить **битовый флаг IMAGE_FILE_UP_SYSTEM_ONLY** к характеристикам выходного заголовка для указания, что это однопроцессорный (UP) драйвер. Операционная система отклонит загрузку UP-драйвера в многопроцессорной (MP) системе.

**/DRIVER:WDM** указывает компоновщику задать **битовый** бит в поле DllCharacteristics дополнительного заголовка.

Если **/Driver** не указан, эти биты установлены компоновщиком.

Если **/Driver** указывается:

- **Компоновщике** в силу. Дополнительные сведения см. в разделе [Параметр /FIXED (фиксированный базовый адрес)](../../build/reference/fixed-fixed-base-address.md).

- Расширение выходного файла будет присвоено sys-файлы. Используйте **/OUT** Чтобы изменить имя файла по умолчанию и расширение. Дополнительные сведения см. в разделе [Параметр /OUT (имя выходного файла)](../../build/reference/out-output-file-name.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **системы** страницу свойств.

1. Изменить **драйвер** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. в разделе [VCLinkerTool.driver свойство](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver?view=visualstudiosdk-2017#Microsoft_VisualStudio_VCProjectEngine_VCLinkerTool_driver).

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
