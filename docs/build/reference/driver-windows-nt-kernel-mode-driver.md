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
ms.openlocfilehash: 5639344ede4007bd66a3d51043f4acb423426b94
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842979"
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER (драйвер режима ядра Windows NT)

>/DRIVER [: ТОЛЬКО ИСТЕЧЕНИЕ |: WDM]

## <a name="remarks"></a>Remarks

Используйте параметр компоновщика **/Driver** для создания драйвера режима ядра Windows NT.

**/Driver: только** в случае, когда компоновщик добавляет **IMAGE_FILE_UP_SYSTEM_ONLY** бит к характеристикам в заголовке Output, чтобы указать, что это драйвер однопроцессорного (up). Операционная система отказывается загружать драйвер в многопроцессорной системе (MP).

**/Driver: WDM** заставляет компоновщик установить **IMAGE_DLLCHARACTERISTICS_WDM_DRIVER** бит в поле DLLCHARACTERISTICS необязательного заголовка.

Если параметр **/Driver** не указан, то эти биты не устанавливаются компоновщиком.

Если задано значение **/Driver** :

- **/Fixed: нет** действующих. Дополнительные сведения см. в разделе [Параметр /FIXED (фиксированный базовый адрес)](fixed-fixed-base-address.md).

- Расширение выходного файла имеет значение. sys. Используйте параметр **/out** для изменения имени файла и расширения по умолчанию. Дополнительные сведения см. в разделе [Параметр /OUT (имя выходного файла)](out-output-file-name.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите папку **компоновщика**.

1. Перейдите на страницу свойств **системы** .

1. Измените свойство **Driver** .

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел [свойство VCLinkerTool. Driver](/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver?view=visualstudiosdk-2017#Microsoft_VisualStudio_VCProjectEngine_VCLinkerTool_driver).

## <a name="see-also"></a>См. также раздел

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
