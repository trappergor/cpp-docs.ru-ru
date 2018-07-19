---
title: Точки входа интерфейса COM | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- entry points, COM interfaces
- state management, OLE/COM interfaces
- MFC COM, COM interface entry points
- OLE, interface entry points
- MFC, managing state data
- COM interfaces, entry points
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d7f52aee6a276410ba6a90fd662a2fad8d258e92
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929891"
---
# <a name="com-interface-entry-points"></a>Точки входа интерфейса COM
Функции-члены интерфейса COM, используйте [METHOD_PROLOGUE](com-interface-entry-points.md#method_prologue) макрос для поддержания соответствующего глобального состояния при вызове методов экспортируемого интерфейса.  
  
 Как правило, функции-члены интерфейсов, реализуемый `CCmdTarget`-производных объектов уже использовать этот макрос для обеспечения автоматической инициализации `pThis` указателя. Пример:  
  
 [!code-cpp[NVC_MFCConnectionPoints#5](../mfc/codesnippet/cpp/com-interface-entry-points_1.cpp)]  
  
 Дополнительные сведения см. в разделе [Технические заметки 38](../mfc/tn038-mfc-ole-iunknown-implementation.md) на MFC/OLE `IUnknown` реализации.  
  
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

