---
title: Редактор изображений для значков | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.cursor.F1
- vc.editors.icon.F1
- vc.editors.cursor
- vc.editors.bitmap.F1
dev_langs:
- C++
helpviewer_keywords:
- editors, images
- resource editors [C++], graphics
- Image editor [C++]
- resource editors [C++], Image editor
ms.assetid: 586d2b8b-0348-4883-a85d-1ff0ddbf14dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fe7cad7fccabd7acc8af7ecf1f3711d5b0d636ce
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379194"
---
# <a name="image-editor-for-icons"></a>Редактор изображений для значков

В редакторе изображений предлагается широкий набор средств для создания и редактирования изображений, а также возможности, которые могут помочь в создании точечных рисунков для панели инструментов. Помимо точечных рисунков, значков и курсоров, можно редактировать изображения в форматах GIF и JPEG при помощи команд меню **Изображение** и средств панели инструментов **Редактор изображений** .

Редактор изображений позволяет выполнять следующие действия:

- [Редактировать графические ресурсы](../windows/editing-graphical-resources-image-editor-for-icons.md)

- [Работать с цветом](../windows/working-with-color-image-editor-for-icons.md)

- [Работать со значками и курсорами: ресурсы изображений для устройств отображения](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)

- [Использовать сочетания клавиш для команд редактора изображений](../windows/accelerator-keys-image-editor-for-icons.md)

**Редактор изображений** окно отображается в двух представлениях изображения, с разделены разделителем две области. Чтобы изменить соотношение областей, переместите разделитель в нужную сторону. Активная панель окружена границами, как выделенная область.

**Редактор изображений** окно может быть настроено в соответствии с вашими пожеланиями и предпочтениями. Вы можете [изменить кратность увеличения](../windows/changing-the-magnification-factor-image-editor-for-icons.md) , а также [отобразить или скрыть пиксельную сетку](../windows/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md).

> [!NOTE]
> С помощью **редактор изображений**, 32-разрядные образы можно просмотреть, но не позволяет их редактировать.

## <a name="visual-studio-image-library"></a>Библиотека изображений Visual Studio

Можно загрузить бесплатно **библиотека изображений Visual Studio** которого содержит много анимации, точечных рисунков и значков, которые можно использовать в приложениях. Дополнительные сведения о том, как загрузить библиотеку, см. в разделе [Библиотека изображений Visual Studio](/visualstudio/designers/the-visual-studio-image-library).

## <a name="managed-resources"></a>Управляемые ресурсы

Можно использовать **изображение** редактора и [двоичный редактор](binary-editor.md) для работы с файлами ресурсов в управляемые проекты. Все управляемые ресурсы, которые нужно редактировать, должны быть связанными ресурсами. Редакторы ресурсов Visual Studio не поддерживают редактирование внедренных ресурсов.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Редакторы ресурсов](../windows/resource-editors.md)<br/>
[Значки](https://msdn.microsoft.com/library/windows/desktop/ms646973.aspx)