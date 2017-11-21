---
title: "Обновление пользовательского интерфейса для представлений записей (доступ к данным MFC) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- user interfaces, updating
- menus, updating as context changes
- record views, user interface
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: aab6ea73fc5726771877640268c89edea4d0745a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="user-interface-updating-for-record-views--mfc-data-access"></a>Обновление пользовательского интерфейса для представлений записей (доступ к данным MFC)
`CRecordView`предоставляет обработчики обновлений пользовательского интерфейса по умолчанию для команд перехода. Эти обработчики автоматически включают и отключают объекты пользовательского интерфейса — пункты меню и кнопки панели инструментов. Мастер приложений предоставляет стандартные меню и, при выборе **Закрепляемая панель инструментов** параметр набор кнопок панели инструментов для команд. Если создан класс представления записей с помощью `CRecordView`, можно добавлять подобные объекты пользовательского интерфейса в приложение.  
  
### <a name="to-create-menu-resources-with-the-menu-editor"></a>Создание ресурсов меню с помощью редактора меню  
  
1.  Сверяясь со сведениями об использовании [редактор меню](../windows/menu-editor.md), создайте собственное меню с аналогичными четырьмя командами.  
  
#### <a name="to-create-toolbar-buttons-with-the-graphics-editor"></a>Создание кнопок панели инструментов с помощью графического редактора  
  
1.  Сверяясь со сведениями об использовании [редактор панелей инструментов](../windows/toolbar-editor.md), отредактируйте ресурс панели инструментов, добавив кнопки панели инструментов для команд перехода.  
  
## <a name="see-also"></a>См. также  
 [Поддержка навигации в представлении записей](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)   
 [Использование представления записей](../data/using-a-record-view-mfc-data-access.md)