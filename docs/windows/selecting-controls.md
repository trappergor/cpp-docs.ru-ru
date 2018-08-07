---
title: Выбор элементов управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Dialog editor, selecting controls
- dominant controls
- dialog box controls, selecting in editor
- controls [C++], selecting
- size, controls
- controls [C++], dominant
ms.assetid: 27f05450-4550-4229-9f4c-2c9e06365596
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5c8a7a57b263fc3db1fa7f021c1a6f4e09c0f8f7
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605673"
---
# <a name="selecting-controls"></a>Выбор элементов управления
Выберите элементы управления до размера, выравнивать, переместить, скопировать, или удалить их и выполните операцию, которую вы хотите. В большинстве случаев необходимо выбрать более одного элемента управления, чтобы использовать средства изменения размера и выравнивания на [редактор диалоговых окон инструментов](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).  
  
 При выборе элемента управления, он имеет затененную рамку вокруг нее с использованием (активный) или пустыми (неактивными) «маркерами» небольшими квадратиками, отображаются в рамки выделенной области. Если выбрано несколько элементов управления, главного элемента управления имеет сплошной маркеров; все другие выбранные элементы управления имеют без заливки маркеров.  
  
 Если размеры или выравнивание нескольких элементов управления, используется редактор диалоговых окон «главного элемента управления» для определения, как размер или выровнены других элементов управления. По умолчанию главного элемента управления является первого выбранного элемента управления.  
  
-   [Выбор нескольких элементов управления](../windows/selecting-multiple-controls.md)  
  
-   [Задание главного элемента управления](../windows/specifying-the-dominant-control.md)  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)   
 [Элементы управления](../mfc/controls-mfc.md)