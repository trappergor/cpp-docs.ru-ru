---
title: "Фабрики классов и прослушивание | Microsoft Docs"
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
  - "vc.mfc.macros.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "фабрики классов, и лицензирование"
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
caps.latest.revision: 13
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Фабрики классов и прослушивание
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Для создания экземпляра элемента управления OLE контейнерное приложение вызывает функцию\-член фабрики класса элемента управления.  Поскольку элемент управления фактический объект OLE, фабрика класса отвечает за создание экземпляров элемента управления.  Каждый класс элемента управления OLE должен иметь фабрику класса.  
  
 Другая важная функциональные возможности элементов управления OLE их возможность принудительного лицензию.  ControlWizard позволяет в объединенный лицензированию во время создания проекта элемента управления.  Дополнительные сведения о лицензировании элементов управления см. в разделе [Элементы управления ActiveX. Лицензировании элементов управления ActiveX](../../mfc/mfc-activex-controls-licensing-an-activex-control.md) статьи.  
  
 В следующей таблице перечислены некоторые макросы и функций, используемых для объявления и реализации фабрики класса элемента управления и в лицензии элемента управления.  
  
### Фабрики класса и лицензирование  
  
|||  
|-|-|  
|[DECLARE\_OLECREATE\_EX](../Topic/DECLARE_OLECREATE_EX.md)|Объявляет фабрику класса элемента управления OLE или страницы свойств.|  
|[IMPLEMENT\_OLECREATE\_EX](../Topic/IMPLEMENT_OLECREATE_EX.md)|Реализует функции `GetClassID` элемента управления и объявляется экземпляр фабрики класса.|  
|[BEGIN\_OLEFACTORY](../Topic/BEGIN_OLEFACTORY.md)|Начинается объявление всех функций лицензирования.|  
|[END\_OLEFACTORY](../Topic/END_OLEFACTORY.md)|Завершает объявление всех функций лицензирования.|  
|[AfxVerifyLicFile](../Topic/AfxVerifyLicFile.md)|Проверяет лицензирован ли элемент управления для использования на определенном компьютере.|  
  
## См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)