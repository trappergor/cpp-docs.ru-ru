---
title: Свойства кнопок панели инструментов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- size, toolbar buttons
- toolbar buttons (in Toolbar editor), setting properties
- Toolbar editor, toolbar button properties
- status bars, active toolbar button text
- command IDs, toolbar buttons
- width, toolbar buttons
ms.assetid: b2705814-7c5d-4f24-8f77-07559b0cdda2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5377616bd026ad9045345a465749f58dc22edd57
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592969"
---
# <a name="toolbar-button-properties"></a>Свойства кнопок панели инструментов

Существуют следующие свойства кнопки панели инструментов.

|Свойство.|Описание:|
|--------------|-----------------|
|**ID**|Определяет идентификатор для кнопки. Выберите в раскрывающемся списке предоставляет Общие **идентификатор** имена.|
|**Ширина**|Задает ширину кнопки. рекомендуется 16 пикселей.|
|**Высота**|Задает высоту кнопки. Обратите внимание на то, что высота кнопки изменяет высоту всех кнопок на панели инструментов. Рекомендуется 15 пикселей.|
|**Запрашивать**|Определяет сообщение, отображаемое в строке состояния. При добавлении \n и именем добавляются всплывающей подсказки для кнопки панели инструментов. Дополнительные сведения см. в разделе [Создание всплывающей подсказки](../windows/creating-a-tool-tip-for-a-toolbar-button.md).|

**Ширина** и **высота** применяются ко всем кнопкам. Битовая карта, используется для создания панели инструментов имеет максимальную ширину 2048. Поэтому если ширина кнопки значение 512, может быть только четыре кнопки, и если ширина присвоено 513, может быть только три кнопки.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

MFC или ATL

## <a name="see-also"></a>См. также

[Изменение свойств кнопки на панели инструментов](../windows/changing-the-properties-of-a-toolbar-button.md)  
[Редактор панелей инструментов](../windows/toolbar-editor.md)