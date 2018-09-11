---
title: Свойства кнопок панели инструментов (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- size, toolbar buttons
- toolbar buttons [C++], setting properties
- Toolbar editor [C++], toolbar button properties
- status bars [C++], active toolbar button text
- command IDs, toolbar buttons
- width, toolbar buttons
ms.assetid: b2705814-7c5d-4f24-8f77-07559b0cdda2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b23194992d3b2bb4f1e2708f7e57396cb7e94be6
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318737"
---
# <a name="toolbar-button-properties-c"></a>Свойства кнопок панели инструментов (C++)

Существуют следующие свойства кнопки панели инструментов.

|Свойство.|Описание|
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