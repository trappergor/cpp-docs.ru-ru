---
title: Создание 256-цветного значка или курсора (редактор изображений для значков)
ms.date: 11/04/2016
helpviewer_keywords:
- 256-color palette
- cursors [C++], color
- colors [C++], icons
- colors [C++], cursors
- icons, color
ms.assetid: 2738089b-4fd3-4c45-96ae-6a15e4c6b780
ms.openlocfilehash: cd1100c05b41017fc89ccf58854cb8ed219a7873
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642767"
---
# <a name="creating-a-256-color-icon-or-cursor-image-editor-for-icons"></a>Создание 256-цветного значка или курсора (редактор изображений для значков)

С помощью **изображение** редактора, значки и курсоры могут быть размера больших (64 × 64) с 256-цветной палитры для выбора. После создания ресурса, выбран стиль изображения устройства.

### <a name="to-create-a-256-color-icon-or-cursor"></a>Создание 256-цветного значка или курсора

1. В [представление ресурсов](../windows/resource-view-window.md), щелкните правой кнопкой мыши RC-файл, а затем выберите **Вставка ресурса** в контекстном меню. (При наличии существующего ресурса изображения в RC-файл, например курсор, вы можете просто щелкните правой кнопкой мыши **курсор** папку и выберите **вставки курсора** в контекстном меню.)

   > [!NOTE]
   > Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

2. В [Вставка ресурса-диалоговое окно](../windows/add-resource-dialog-box.md)выберите **значок** или **курсор** и нажмите кнопку **New**.

3. На **изображение** меню, щелкните **изображения для устройства**.

4. Выберите нужный стиль 256-цветного изображение.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Использование 256-цветной палитры](../windows/using-the-256-color-palette-image-editor-for-icons.md)<br/>
[Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Значки и курсоры: ресурсы изображений для устройств отображения](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)