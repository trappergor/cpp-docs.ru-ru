---
title: 'Значки и курсоры: ресурсы изображений для устройств отображения (редактор C++ изображений для значков) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- cursors [C++], creating
- image resources [C++], display devices
- icons [C++], creating
- cursors [C++], types
- icons [C++]
- Image editor [C++], icons and cursors
- cursors [C++]
- display devices [C++], creating icons for
- cursors [C++], hot spots
- icons [C++], types
ms.assetid: 8f0809a8-0cf0-4da9-b23d-51f28bf15f5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d3a34613d3a8d88166cbfca123c2318e87f024e6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436771"
---
# <a name="icons-and-cursors-image-resources-for-display-devices-c-image-editor-for-icons"></a>Значки и курсоры: ресурсы изображений для устройств отображения (редактор C++ изображений для значков)

Значки и курсоры представляют собой графические ресурсы, которые могут состоять из нескольких изображений разных размеров, использующих разные цветовые схемы, в зависимости от типа устройства отображения. Кроме того, у курсоров есть "активная точка" — точка, которая используется системой Windows для отслеживания позиции курсора. Значки и курсоры будут созданы и отредактированы с использованием **изображение** редактора, как точечные рисунки и другие образы.

При создании значка или курсора, **изображение** редактор сначала появляется изображение стандартного типа. Это изображение сначала заполняется цветом экрана (прозрачным). Если изображение является курсором, его активная точка изначально находится в левом верхнем углу (и имеет координаты 0,0).

По умолчанию **изображение** редактор поддерживает создание дополнительных образов для устройств, представленных в следующей таблице. Чтобы создать изображения для других устройств, необходимо задать ширину, высоту и количество цветов в [диалоговом окне "Настраиваемое изображение"](custom-image-dialog-box-image-editor-for-icons.md).

> [!NOTE]
> С помощью **редактор изображений**, 32-разрядные образы можно просмотреть, но не позволяет их редактировать.

|Цвет|Ширина (в пикселях)|Высота (в пикселях)|
|-----------|----------------------|-----------------------|
|Монохромный|16|16|
|Монохромный|32|32|
|Монохромный|48|48|
|Монохромный|64|64|
|Монохромный|96|96|
|16|16|16|
|16|32|32|
|16|64|64|
|16|48|48|
|16|96|96|
|256|16|16|
|256|32|32|
|256|48|48|
|256|64|64|
|256|96|96|

- [Создание изображения (значка или курсора) для устройства](../windows/creating-a-device-image-image-editor-for-icons.md)

- [Добавление изображения для другого устройства отображения](../windows/adding-an-image-for-a-different-display-device-image-editor-for-icons.md)

- [Копирование изображения устройства](../windows/copying-a-device-image-image-editor-for-icons.md)

- [Удаление изображения устройства](../windows/deleting-a-device-image-image-editor-for-icons.md)

- [Создание прозрачных областей или областей с обращенными цветами на изображениях устройств](../windows/creating-transparent-or-inverse-regions-in-device-images.md)

- [Создание 256-цветного значка или курсора](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)

- [Настройка активной точки курсора](../windows/setting-a-cursor-s-hot-spot-image-editor-for-icons.md)

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Редактор изображений для значков](../windows/image-editor-for-icons.md)<br/>
[Значки](https://msdn.microsoft.com/library/windows/desktop/ms646973)<br/>
[Курсоры](https://msdn.microsoft.com/library/windows/desktop/ms646970)