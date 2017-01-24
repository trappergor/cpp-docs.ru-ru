---
title: "Точки входа интерфейса COM | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "интерфейсы COM, точки входа"
  - "точки входа, интерфейсы COM"
  - "MFC COM, точки входа интерфейса COM"
  - "MFC - библиотека, управление данными состояния"
  - "OLE, точки входа интерфейса"
  - "управление состоянием, интерфейсы OLE/COM"
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Точки входа интерфейса COM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для функций\-членов COM\-интерфейса используйте макрос [METHOD\_PROLOGUE](../Topic/METHOD_PROLOGUE.md) для обеспечения правильного глобального состояния при вызове методов экспортированного интерфейса.  
  
 Как правило, функции\-члены интерфейсов, реализованных `CCmdTarget`\- производные объекты уже используют этот макрос, чтобы обеспечить автоматическую инициализацию указателя `pThis`.  Примеры.  
  
 [!code-cpp[NVC_MFCConnectionPoints#5](../mfc/codesnippet/CPP/com-interface-entry-points_1.cpp)]  
  
 Дополнительные сведения см. в разделе [Техническое примечание 38](../mfc/tn038-mfc-ole-iunknown-implementation.md) для реализации MFC\/OLE **IUnknown**.  
  
 Макрос `METHOD_PROLOGUE` определяется следующим образом:  
  
 `#define METHOD_PROLOGUE(theClass, localClass) \`  
  
 `theClass* pThis = \`  
  
 `((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \`  
  
 `AFX_MANAGE_STATE(pThis->m_pModuleState) \`  
  
 Часть макроса связанного с управлением глобального состояния выглядит следующим образом:  
  
 `AFX_MANAGE_STATE( pThis->m_pModuleState )`  
  
 В этом выражении предполагается, что будет *m\_pModuleState* переменной\-членом, содержащего объекта.  Он реализуется базовый класс `CCmdTarget` и инициализируется в соответствующее значение `COleObjectFactory`, когда объект экземпляра.  
  
## См. также  
 [Управление данными состояния модулей MFC](../mfc/managing-the-state-data-of-mfc-modules.md)