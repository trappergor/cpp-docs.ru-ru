---
title: "Класс CDocItem | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocItem
- AFXOLE/CDocItem
- AFXOLE/CDocItem::GetDocument
- AFXOLE/CDocItem::IsBlank
dev_langs:
- C++
helpviewer_keywords:
- CDocItem [MFC], GetDocument
- CDocItem [MFC], IsBlank
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8a4987554965674612eaf8d9aa78c659f7f28b75
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdocitem-class"></a>Класс CDocItem
Базовый класс для элементов документа, являющихся компонентами данных документа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDocItem : public CCmdTarget  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDocItem::GetDocument](#getdocument)|Возвращает документ, который содержит элемент.|  
|[CDocItem::IsBlank](#isblank)|Определяет, содержит ли элемент никакой информации.|  
  
## <a name="remarks"></a>Примечания  
 `CDocItem`объекты используются для представления элементов OLE в документах клиента и сервера.  
  
 Дополнительные сведения см. в статье [контейнеры: реализация контейнера](../../mfc/containers-implementing-a-container.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocItem`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="getdocument"></a>CDocItem::GetDocument  
 Вызовите эту функцию для получения документа, который содержит элемент.  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на документ, который содержит элемент. **NULL**, если элемент не является частью документа.  
  
### <a name="remarks"></a>Примечания  
 Эта функция переопределяется в производных классах [COleClientItem](../../mfc/reference/coleclientitem-class.md) и [COleServerItem](../../mfc/reference/coleserveritem-class.md), возвращающая указатель на любой [COleDocument](../../mfc/reference/coledocument-class.md), [ COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), или [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) объекта.  
  
##  <a name="isblank"></a>CDocItem::IsBlank  
 Вызывается платформой при сериализации по умолчанию.  
  
```  
virtual BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент не содержит сведений; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `CDocItem` объекта не может быть пустым. [COleClientItem](../../mfc/reference/coleclientitem-class.md) объектов иногда пусты, так как они наследуются непосредственно `CDocItem`. Тем не менее [COleServerItem](../../mfc/reference/coleserveritem-class.md) объекты всегда пусты. По умолчанию, содержащий приложения OLE `COleClientItem` объекты, которые не имеют x или y сериализуются экстента. Это делается путем возвращения **TRUE** из переопределения события `IsBlank` Если элемент не имеет x или y экстента.  
  
 Переопределите эту функцию, если вы хотите применить другие действия во время сериализации.  
  
## <a name="see-also"></a>См. также  
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDocument](../../mfc/reference/coledocument-class.md)   
 [Класс COleServerItem](../../mfc/reference/coleserveritem-class.md)   
 [Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)
