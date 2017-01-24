---
title: "Управление приложением | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элемент управления приложением"
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
caps.latest.revision: 12
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Управление приложением
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE требует существенного элемента управления с приложениями и их объектами.  OLE системные библиотеки DLL должны иметь возможность запустить и выпуска приложения автоматически, координируйте их работы и изменение объектов и т д  Функции в этом разделе отвечают их.  Помимо вызывалась OLE системных библиотек DLL, эти функции должны быть также иногда называют приложениями.  
  
### Элемент управления приложениями  
  
|||  
|-|-|  
|[AfxOleCanExitApp](../Topic/AfxOleCanExitApp.md)|Указывает, является ли приложение может завершить.|  
|[AfxOleGetMessageFilter](../Topic/AfxOleGetMessageFilter.md)|Получает текущий фильтр сообщений приложения.|  
|[AfxOleGetUserCtrl](../Topic/AfxOleGetUserCtrl.md)|Получает текущий флажок пользовательского элемента управления.|  
|[AfxOleSetUserCtrl](../Topic/AfxOleSetUserCtrl.md)|Получает или очищает флажок пользовательского элемента управления.|  
|[AfxOleLockApp](../Topic/AfxOleLockApp.md)|Увеличивает число платформы глобальное числа активных объектов в приложении.|  
|[AfxOleUnlockApp](../Topic/AfxOleUnlockApp.md)|Уменьшает значение счетчика платформы числа активных объектов в приложении.|  
|[AfxOleRegisterServerClass](../Topic/AfxOleRegisterServerClass.md)|Регистрирует сервер в системном реестре OLE.|  
|[AfxOleSetEditMenu](../Topic/AfxOleSetEditMenu.md)|Реализует интерфейс для объекта команды *typename*.|  
  
## См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)