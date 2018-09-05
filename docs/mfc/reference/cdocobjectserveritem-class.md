---
title: Класс CDocObjectServerItem | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::GetDocument
- AFXDOCOB/CDocObjectServerItem::OnHide
- AFXDOCOB/CDocObjectServerItem::OnShow
dev_langs:
- C++
helpviewer_keywords:
- CDocObjectServerItem [MFC], CDocObjectServerItem
- CDocObjectServerItem [MFC], GetDocument
- CDocObjectServerItem [MFC], OnHide
- CDocObjectServerItem [MFC], OnShow
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 985333deaeceeed594e11223c417f3217e8b0322
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43682047"
---
# <a name="cdocobjectserveritem-class"></a>Класс CDocObjectServerItem
Реализует команды OLE-сервера специально для серверов DocObject.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDocObjectServerItem : public COleServerItem  
```  
  
## <a name="members"></a>Участники  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|Создает объект `CDocObjectServerItem`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDocObjectServerItem::GetDocument](#getdocument)|Извлекает указатель на документ, который содержит элемент.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDocObjectServerItem::OnDoVerb](#ondoverb)|Создает исключение, если платформа пытается скрыть элемент DocObject.|
|[CDocObjectServerItem::OnHide](#onhide)|Создает исключение, если платформа пытается скрыть элемент DocObject.|  
|[CDocObjectServerItem::OnShow](#onshow)|Вызывается платформой, чтобы сделать DocObject элемента на месте active. Если элемент не DocObject, вызывает [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow).|  
  
## <a name="remarks"></a>Примечания  
 `CDocObjectServerItem` Определяет функции является переопределяемым элементом: [OnHide](#onhide), [OnDoVerb](#ondoverb), и [OnShow](#onshow).  
  
 Для использования `CDocObjectServerItem`, убедиться, что [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) в переопределите вашей `COleServerDoc`-производном классе возвращает новый `CDocObjectServerItem` объекта. Если вам нужно изменить функциональные возможности элемента, можно создать новый экземпляр собственного `CDocObjectServerItem`-производного класса.  
  
 Дополнительные сведения о DocObjects см. в разделе [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) и [COleCmdUI](../../mfc/reference/colecmdui-class.md) в *Справочник по библиотеке MFC*. Также см. в разделе [Internet первые шаги: активные документы](../../mfc/active-documents-on-the-internet.md) и [активные документы](../../mfc/active-documents-on-the-internet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleServerItem](../../mfc/reference/coleserveritem-class.md)  
  
 `CDocObjectServerItem`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdocob.h  
  
##  <a name="cdocobjectserveritem"></a>  CDocObjectServerItem::CDocObjectServerItem  
 Создает объект `CDocObjectServerItem`.  
  
```  
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Параметры  
 *pServerDoc*  
 Указатель на документ, который будет содержать новый элемент DocObject.  
  
 *bAutoDelete*  
 Указывает, может ли быть удален объект при отпускании ссылку на него. Установите значение FALSE, если аргумент `CDocObjectServerItem` объект является неотъемлемой частью данных документа. Задано значение TRUE, если объект является вторичной структура, используемая для определения диапазона в данных документа, которые могут удаляться платформой.  
  
##  <a name="getdocument"></a>  CDocObjectServerItem::GetDocument  
 Извлекает указатель на документ, который содержит элемент.  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на документ, который содержит элемент; Значение NULL, если элемент не является частью документа.  
  
### <a name="remarks"></a>Примечания  
 Это позволяет доступ к документу сервера, который передается в качестве аргумента для [CDocObjectServerItem](#cdocobjectserveritem) конструктор.  
  
##  <a name="onhide"></a>  CDocObjectServerItem::OnHide  
 Вызвано структурой для скрытия элемента.  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает исключение, если элемент является DocObject. Не удается скрыть active DocObject элемент, так как она использует представление целиком. Необходимо отключить элемент DocObject, чтобы убрать его. Если элемент не DocObject, реализация по умолчанию вызывает [COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide).  
  
##  <a name="onshow"></a>  CDocObjectServerItem::OnShow  
 Вызывается платформой для указания серверное приложение, чтобы сделать DocObject элемента на месте active.  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>Примечания  
 Если элемент не DocObject, реализация по умолчанию вызывает [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen). Переопределите эту функцию, если вы хотите выполнить специальная обработка при открытии элемента DocObject.  
  
## <a name="see-also"></a>См. также  
 [Класс COleServerItem](../../mfc/reference/coleserveritem-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md)   
 [Класс COleDocObjectItem](../../mfc/reference/coledocobjectitem-class.md)
