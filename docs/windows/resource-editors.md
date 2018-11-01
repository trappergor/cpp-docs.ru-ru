---
title: Редакторы ресурсов (C++)
ms.date: 11/04/2016
f1_keywords:
- vs.editors.resource
- vc.resvw.resource.editors
- vs.resvw.resource.editors
helpviewer_keywords:
- editors [C++], resource
- editors [C++]
- resource editors
- Windows [C++], application resource editing
ms.assetid: e20a29ec-d6fb-4ead-98f3-431a0e23aaaf
ms.openlocfilehash: ae35dbe98304fbf2f80dfe5cba8747d47cbba4d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622408"
---
# <a name="resource-editors"></a>редакторы ресурсов

Объект **ресурсов** редактор представляет собой специализированную среду для создания и изменения ресурсов, включенных в проект Visual Studio. Редакторы ресурсов Visual Studio используют общий набор способов и интерфейсов, упрощая и ускоряя создание и изменение ресурсов приложения. Редакторы ресурсов позволяют [просматривать и изменять ресурсы в соответствующем редакторе](../windows/viewing-and-editing-resources-in-a-resource-editor.md) , а также [предварительно просматривать ресурсы](../windows/previewing-resources.md).

Соответствующий редактор открывается автоматически при создании или открытии ресурса.

**Примечание** .   Поскольку в проектах управляемого кода не используются файлы описания ресурсов, ресурсы необходимо открывать из **обозревателя решений**. Для работы с файлами ресурсов в управляемых проектах можно использовать [редактор изображений](../windows/image-editor-for-icons.md) и [двоичный редактор](binary-editor.md) . Все управляемые ресурсы, которые нужно редактировать, должны быть связанными ресурсами. Редакторы ресурсов Visual Studio не поддерживают редактирование внедренных ресурсов.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

|Редактор|Редактируемый элемент|
|----------------|----------------|
|[Редактор сочетаний клавиш](../windows/accelerator-editor.md)|Таблицы сочетаний клавиш в проектах Visual C++|
|[Binary Editor](binary-editor.md)|Двоичные данные и настраиваемые ресурсы в проектах Visual C++, Visual Basic или Visual C#|
|[Редактор диалоговых окон](../windows/dialog-editor.md)|Диалоговые окна в проектах Visual C++|
|[Image Editor](../windows/image-editor-for-icons.md)|Точечные рисунки, значки, курсоры и другие файлы изображений в проектах Visual C++, Visual Basic или Visual C#|
|[Редактор меню](../windows/menu-editor.md)|Ресурсы меню в проектах Visual C++|
|[Редактор ленты (Ribbon)](../mfc/ribbon-designer-mfc.md)|Ресурсы ленты в проектах MFC|
|[Редактор строк](../windows/string-editor.md)|Таблицы строк в проектах Visual C++|
|[Редактор панелей инструментов](../windows/toolbar-editor.md)|Ресурсы панелей инструментов в проектах Visual C++ Редактор панелей инструментов входит в состав редактора изображений.|
|[Редактор сведений о версии](../windows/version-information-editor.md)|Сведения о версиях в проектах Visual C++|

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Работа с файлами ресурсов](../windows/working-with-resource-files.md)<br/>
[Файлы ресурсов](../windows/resource-files-visual-studio.md)<br/>
[Символы: идентификаторы ресурсов](../windows/symbols-resource-identifiers.md)<br/>
[Меню и другие ресурсы](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)