---
title: Класс CDocObjectServerItem | Документы Microsoft
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
ms.openlocfilehash: 30daf42d54b66d4e3c4ad47a406748ab023be79d
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956637"
---
# <a name="cdocobjectserveritem-class"></a>Класс CDocObjectServerItem
Реализует команды OLE-сервера специально для серверов DocObject.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDocObjectServerItem : public COleServerItem  
```  
  
## <a name="members"></a>Участники  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|Создает объект `CDocObjectServerItem`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDocObjectServerItem::GetDocument](#getdocument)|Извлекает указатель на документ, содержащий элемент.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDocObjectServerItem::OnHide](#onhide)|Вызывает исключение, если платформа framework пытается скрывать DocObject.|  
|[CDocObjectServerItem::OnShow](#onshow)|Вызывается платформой, чтобы сделать DocObject элемента на месте active. Если элемент не DocObject, вызывает [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow).|  
  
## <a name="remarks"></a>Примечания  
 `CDocObjectServerItem` Определяет функции переопределяемый член: [OnHide](#onhide), [OnOpen](http://msdn.microsoft.com/en-us/7a9b1363-6ad8-4732-9959-4e35c07644fd), и [OnShow](#onshow).  
  
 Для использования `CDocObjectServerItem`, обеспечить [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) переопределить в вашей `COleServerDoc`-производного класса возвращает новую `CDocObjectServerItem` объекта. Если необходимо изменить функциональные возможности в элемент, можно создать новый экземпляр собственного `CDocObjectServerItem`-производного класса.  
  
 Дополнительные сведения о DocObjects см. в разделе [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) и [COleCmdUI](../../mfc/reference/colecmdui-class.md) в *Справочник по библиотеке MFC*. См. также [первые шаги в Интернете: активные документы](../../mfc/active-documents-on-the-internet.md) и [активные документы](../../mfc/active-documents-on-the-internet.md).  
  
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
 Указывает, является ли объект может быть удален при отпускании ссылку на него. Значение аргумента **FALSE** Если `CDocObjectServerItem` объект является неотъемлемой частью данных в документе. Задайте для него значение **TRUE** Если объект является вторичной структура, используемая для определения диапазона данных в документе, могут быть удалены платформой.  
  
##  <a name="getdocument"></a>  CDocObjectServerItem::GetDocument  
 Извлекает указатель на документ, содержащий элемент.  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на документ, который содержит элемент. **NULL** Если элемент не является частью документа.  
  
### <a name="remarks"></a>Примечания  
 Это позволяет получить доступ к документу сервера, который передается в качестве аргумента для [CDocObjectServerItem](#cdocobjectserveritem) конструктор.  
  
##  <a name="onhide"></a>  CDocObjectServerItem::OnHide  
 Вызывается платформой для скрытия элемента.  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает исключение, если элемент является DocObject. Невозможно скрыть active DocObject элемент, так как она использует представление целиком. Необходимо отключить DocObject элемента, чтобы он исчезнет. Если элемент не DocObject, реализация по умолчанию вызывает [COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide).  
  
##  <a name="onshow"></a>  CDocObjectServerItem::OnShow  
 Вызывается платформой, чтобы дать указание серверное приложение, чтобы сделать DocObject элемента на месте active.  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>Примечания  
 Если элемент не DocObject, реализация по умолчанию вызывает [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen). Если вы хотите выполнить специальная обработка при открытии элемента DocObject переопределите эту функцию.  
  
## <a name="see-also"></a>См. также  
 [Класс COleServerItem](../../mfc/reference/coleserveritem-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md)   
 [Класс COleDocObjectItem](../../mfc/reference/coledocobjectitem-class.md)
