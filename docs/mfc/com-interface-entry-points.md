---
title: "Точки входа интерфейса COM | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- entry points, COM interfaces
- state management, OLE/COM interfaces
- MFC COM, COM interface entry points
- OLE, interface entry points
- MFC, managing state data
- COM interfaces, entry points
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 010df3546a6ac2b6276281c39efdd76abd5ec222
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="com-interface-entry-points"></a>Точки входа интерфейса COM
Функции-члены интерфейса COM, используйте [METHOD_PROLOGUE](com-interface-entry-points.md#method_prologue) макрос для поддержания соответствующего глобального состояния при вызове методов экспортируемого интерфейса.  
  
 Как правило, функции-члены интерфейсов, реализуемый `CCmdTarget`-производных объектов уже использовать этот макрос для обеспечения автоматической инициализации `pThis` указателя. Пример:  
  
 [!code-cpp[NVC_MFCConnectionPoints#5](../mfc/codesnippet/cpp/com-interface-entry-points_1.cpp)]  
  
 Дополнительные сведения см. в разделе [Технические заметки 38](../mfc/tn038-mfc-ole-iunknown-implementation.md) на MFC/OLE **IUnknown** реализации.  
  
 `METHOD_PROLOGUE` Макрос определяется как:  
  
 `#define METHOD_PROLOGUE(theClass, localClass) \`  
  
 `theClass* pThis = \`  
  
 `((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \`  
  
 `AFX_MANAGE_STATE(pThis->m_pModuleState) \`  
  
 Часть макрос, касающиеся управления глобальное состояние — это:  
  
 `AFX_MANAGE_STATE( pThis->m_pModuleState )`  
  
 В этом выражении *m_pModuleState* полагается равным переменной-члена вмещающего объекта. Она реализуется `CCmdTarget` базового класса и инициализируется с соответствующим значением, `COleObjectFactory`, при создании экземпляра объекта.  
  
## <a name="see-also"></a>См. также  
 [Управление данными состояния модулей MFC](../mfc/managing-the-state-data-of-mfc-modules.md)

