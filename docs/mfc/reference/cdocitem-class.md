---
title: Класс CDocItem | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 88c30418f886cd791a7119367c5ddbccc19003fa
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335585"
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
|[CDocItem::GetDocument](#getdocument)|Возвращает документ, содержащий элемент.|  
|[CDocItem::IsBlank](#isblank)|Определяет, содержит ли данные.|  
  
## <a name="remarks"></a>Примечания  
 `CDocItem` объекты используются для представления элементов OLE в документах клиента и сервера.  
  
 Дополнительные сведения см. в статье [контейнеры: реализация контейнера](../../mfc/containers-implementing-a-container.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocItem`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="getdocument"></a>  CDocItem::GetDocument  
 Вызывайте эту функцию, чтобы получить документ, который содержит элемент.  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на документ, который содержит элемент; Значение NULL, если элемент не является частью документа.  
  
### <a name="remarks"></a>Примечания  
 Эта функция переопределен в производных классах [COleClientItem](../../mfc/reference/coleclientitem-class.md) и [COleServerItem](../../mfc/reference/coleserveritem-class.md), возвращающая указатель на либо [COleDocument](../../mfc/reference/coledocument-class.md), [ COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), или [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) объекта.  
  
##  <a name="isblank"></a>  CDocItem::IsBlank  
 Вызывается платформой при сериализации по умолчанию.  
  
```  
virtual BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент не содержит сведений; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `CDocItem` объекты не являются пустыми. [COleClientItem](../../mfc/reference/coleclientitem-class.md) объектов иногда пусты, так как они являются производными непосредственно из `CDocItem`. Тем не менее [COleServerItem](../../mfc/reference/coleserveritem-class.md) объекты всегда будут пустыми. По умолчанию приложений OLE, содержащих `COleClientItem` объекты, которые не имеют x или y сериализуются экстента. Это можно сделать, возвращая TRUE из переопределения `IsBlank` Если элемент не имеет x или y экстента.  
  
 Переопределите эту функцию, если вы хотите реализовать другие действия во время сериализации.  
  
## <a name="see-also"></a>См. также  
 [Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDocument](../../mfc/reference/coledocument-class.md)   
 [Класс COleServerItem](../../mfc/reference/coleserveritem-class.md)   
 [Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)
