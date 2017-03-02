---
title: "Класс CDocItem | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocItem
dev_langs:
- C++
helpviewer_keywords:
- items, document
- document items
- server documents, document items
- CDocItem class
- container document items
- client document items
- OLE documents, items
- server documents
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 1ade88aa562180d5c3a6a7afe3fe26943a5d811d
ms.lasthandoff: 02/24/2017

---
# <a name="cdocitem-class"></a>Класс CDocItem
Базовый класс для элементов документа, являющихся компонентами данных документа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDocItem : public CCmdTarget  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
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
  
##  <a name="a-namegetdocumenta--cdocitemgetdocument"></a><a name="getdocument"></a>CDocItem::GetDocument  
 Эта функция вызывается для возврата документа, который содержит элемент.  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на документ, который содержит элемент. **NULL**, если элемент не является частью документа.  
  
### <a name="remarks"></a>Примечания  
 Эта функция переопределяется в производных классах [COleClientItem](../../mfc/reference/coleclientitem-class.md) и [производного от COleServerItem](../../mfc/reference/coleserveritem-class.md), возвращающая указатель на любой [COleDocument](../../mfc/reference/coledocument-class.md), [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), или [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) объекта.  
  
##  <a name="a-nameisblanka--cdocitemisblank"></a><a name="isblank"></a>CDocItem::IsBlank  
 Вызывается инфраструктурой при сериализации по умолчанию.  
  
```  
virtual BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент не содержит сведений; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `CDocItem` объекта не может быть пустым. [COleClientItem](../../mfc/reference/coleclientitem-class.md) объектов иногда пусты, поскольку они наследуются непосредственно `CDocItem`. Тем не менее [производного от COleServerItem](../../mfc/reference/coleserveritem-class.md) объекты всегда пусты. По умолчанию, содержащий приложения OLE `COleClientItem` объекты, которые не имеют x или y степени сериализуются. Это делается путем возвращения **TRUE** из переопределения события `IsBlank` Если элемент не имеет x или y экстента.  
  
 Переопределите эту функцию, если вы хотите реализовать другие действия во время сериализации.  
  
## <a name="see-also"></a>См. также  
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDocument](../../mfc/reference/coledocument-class.md)   
 [Класса, производного от COleServerItem](../../mfc/reference/coleserveritem-class.md)   
 [Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)

