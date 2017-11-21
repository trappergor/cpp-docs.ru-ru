---
title: "Свойства кнопок панели инструментов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- size, toolbar buttons
- toolbar buttons (in Toolbar editor), setting properties
- Toolbar editor, toolbar button properties
- status bars, active toolbar button text
- command IDs, toolbar buttons
- width, toolbar buttons
ms.assetid: b2705814-7c5d-4f24-8f77-07559b0cdda2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 98c78922ee3987bf459f01a62253e9835ad3e377
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="toolbar-button-properties"></a>Свойства кнопок панели инструментов
Существуют следующие свойства кнопки панели инструментов.  
  
|Свойство|Описание|  
|--------------|-----------------|  
|**ID**|Определяет идентификатор для кнопки. Предоставляет общие раскрывающегося списка **идентификатор** имена.|  
|**Ширина**|Задает ширину кнопки. рекомендуется 16 пикселей.|  
|**Высота**|Задает высоту кнопки. Обратите внимание, что высота кнопки изменяет высоту всех кнопок на панели инструментов. Рекомендуется 15 пикселей.|  
|**Запрашивать**|Определяет сообщение, отображаемое в строке состояния. Добавление \n и имя появится всплывающая подсказка для кнопки панели инструментов. Дополнительные сведения см. в разделе [Создание всплывающей подсказки](../windows/creating-a-tool-tip-for-a-toolbar-button.md).|  
  
 **Ширина** и **высота** применяются ко всем кнопкам. Точечный рисунок, который используется для создания панели инструментов имеет максимальную ширину 2048. Поэтому если ширина кнопки значение 512, можно установить только четыре кнопки, и что задайте ширину 513, может иметь только три кнопки.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](https://msdn.microsoft.com/library/f45fce5x.aspx) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](https://msdn.microsoft.com/library/xbx3z216.aspx). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
## <a name="requirements"></a>Требования  
 MFC или ATL  
  
## <a name="see-also"></a>См. также  
 [Изменение свойств кнопки панели инструментов](../windows/changing-the-properties-of-a-toolbar-button.md)   
 [Редактор панелей инструментов](../windows/toolbar-editor.md)

