---
title: /DRIVER (драйвер режима ядра Windows NT)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.driver
- /driver
helpviewer_keywords:
- kernel mode driver
- -DRIVER linker option
- DRIVER linker option
- /DRIVER linker option
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
ms.openlocfilehash: ab7253d7e386bf385bcb3a586c5e0e1c1e860694
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293112"
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER (драйвер режима ядра Windows NT)

>/ DRIVER [: UPONLY |: WDM]

## <a name="remarks"></a>Примечания

Используйте **/Driver** параметр компоновщика для сборки драйвера режима ядра Windows NT.

**/DRIVER:UPONLY** указывает компоновщику добавить **битовый флаг IMAGE_FILE_UP_SYSTEM_ONLY** к характеристикам выходного заголовка для указания, что это однопроцессорный (UP) драйвер. Операционная система отклонит загрузку UP-драйвера в многопроцессорной (MP) системе.

**/DRIVER:WDM** указывает компоновщику задать **битовый** бит в поле DllCharacteristics дополнительного заголовка.

Если **/Driver** не указан, эти биты установлены компоновщиком.

Если **/Driver** указывается:

- **Компоновщике** в силу. Дополнительные сведения см. в разделе [Параметр /FIXED (фиксированный базовый адрес)](fixed-fixed-base-address.md).

- Расширение выходного файла будет присвоено sys-файлы. Используйте **/OUT** Чтобы изменить имя файла по умолчанию и расширение. Дополнительные сведения см. в разделе [Параметр /OUT (имя выходного файла)](out-output-file-name.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **системы** страницу свойств.

1. Изменить **драйвер** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. в разделе [VCLinkerTool.driver свойство](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver?view=visualstudiosdk-2017#Microsoft_VisualStudio_VCProjectEngine_VCLinkerTool_driver).

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
