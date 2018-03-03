---
title: "Задание местоположения и размера диалогового окна | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, size
- dialog boxes, positioning
ms.assetid: 2b7c495e-6595-4cfb-9664-80b2826d0851
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 03c4c6d6afb13a0e4ed8801838356ff0d1e851f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="specifying-the-location-and-size-of-a-dialog-box"></a>Задание местоположения и размера диалогового окна
Расположение и размер диалогового окна, а также расположение и размер элементов управления, измеряется в диалоговых единицах. Значения для отдельных элементов управления и диалогового окна отображаются в правом нижнем углу строки при выборе состояния Visual Studio.  
  
 Существует три свойства, которые можно установить в [окно "Свойства"](/visualstudio/ide/reference/properties-window) чтобы указать, где оно появится на экране. Свойство Center является логическим. Если значение равно True, диалоговое окно всегда будет отображаться в центре экрана. Если присвоить ему значение False, затем можно задать свойства XPos и YPos для явного определения, где на экране появится диалоговое окно. Положение свойства имеют значения смещения от верхнего левого угла области просмотра, которая определяется как {X = 0, Y = 0}. Позиция также основана на **абсолютное выравнивание** свойство: значение True, если координаты указываются относительно экрана; Если значение равно False, координаты указываются относительно владельца диалогового окна.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)   
 [Элементы управления](../mfc/controls-mfc.md)

