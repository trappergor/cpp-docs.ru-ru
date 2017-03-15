---
title: "Класс CDocObjectServerItem | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocObjectServerItem
dev_langs:
- C++
helpviewer_keywords:
- document object server
- CDocObjectServerItem class
- servers [C++], ActiveX documents
- docobject server
- servers [C++], doc objects
- ActiveX documents [C++], document server
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
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
ms.openlocfilehash: 06cf873512fbf43b729d9a70f185582a4e48cafc
ms.lasthandoff: 02/24/2017

---
# <a name="cdocobjectserveritem-class"></a>Класс CDocObjectServerItem
Реализует команды OLE-сервера специально для серверов DocObject.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDocObjectServerItem : public COleServerItem  
```  
  
## <a name="members"></a>Члены  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|Создает объект `CDocObjectServerItem`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDocObjectServerItem::GetDocument](#getdocument)|Извлекает указатель на документ, содержащий элемент.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDocObjectServerItem::OnHide](#onhide)|Вызывает исключение, если платформа framework пытается скрыть элемент DocObject.|  
|[CDocObjectServerItem::OnShow](#onshow)|Вызывается платформой вносить DocObject элемента на месте active. Если элемент не DocObject, вызывает [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow).|  
  
## <a name="remarks"></a>Примечания  
 `CDocObjectServerItem`Определяет переопределяемый член функции: [OnHide](#onhide), [OnOpen](http://msdn.microsoft.com/en-us/7a9b1363-6ad8-4732-9959-4e35c07644fd), и [OnShow](#onshow).  
  
 Для использования `CDocObjectServerItem`, обеспечить [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) переопределить в вашей `COleServerDoc`-производного класса возвращает новый `CDocObjectServerItem` объекта. Если необходимо изменить функциональные возможности в ваш элемент, можно создать новый экземпляр собственного `CDocObjectServerItem`-производного класса.  
  
 Дополнительные сведения о DocObjects в разделе [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) и [COleCmdUI](../../mfc/reference/colecmdui-class.md) в *Справочник по библиотеке MFC*. См. также [Интернет первые шаги: активные документы](../../mfc/active-documents-on-the-internet.md) и [активные документы](../../mfc/active-documents-on-the-internet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [Производного от COleServerItem](../../mfc/reference/coleserveritem-class.md)  
  
 `CDocObjectServerItem`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdocob.h  
  
##  <a name="a-namecdocobjectserveritema--cdocobjectserveritemcdocobjectserveritem"></a><a name="cdocobjectserveritem"></a>CDocObjectServerItem::CDocObjectServerItem  
 Создает объект `CDocObjectServerItem`.  
  
```  
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Параметры  
 `pServerDoc`  
 Указатель на документ, который будет содержать новый элемент DocObject.  
  
 `bAutoDelete`  
 Указывает, может ли быть удален объект при отпускании ссылку на него. Значение аргумента **FALSE** Если `CDocObjectServerItem` объект является неотъемлемой частью данных в документе. Задайте для него значение **TRUE** Если объект получателя структура, используемая для определения диапазона данных в документе, могут быть удалены по платформе.  
  
##  <a name="a-namegetdocumenta--cdocobjectserveritemgetdocument"></a><a name="getdocument"></a>CDocObjectServerItem::GetDocument  
 Извлекает указатель на документ, содержащий элемент.  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на документ, который содержит элемент. **NULL** Если элемент не является частью документа.  
  
### <a name="remarks"></a>Примечания  
 Это позволяет получить доступ для серверного документа, которая передается в качестве аргумента для [CDocObjectServerItem](#cdocobjectserveritem) конструктор.  
  
##  <a name="a-nameonhidea--cdocobjectserveritemonhide"></a><a name="onhide"></a>CDocObjectServerItem::OnHide  
 Вызывается платформой для скрытия элемента.  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию создает исключение, если элемент является DocObject. Невозможно скрыть активный элемент DocObject уходит всего представления. Необходимо отключить исчезал DocObject элемента. Если элемент не DocObject, реализация по умолчанию вызывает [COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide).  
  
##  <a name="a-nameonshowa--cdocobjectserveritemonshow"></a><a name="onshow"></a>CDocObjectServerItem::OnShow  
 Вызывается платформой для указания сервера приложению выполнять DocObject элемента на месте active.  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>Примечания  
 Если элемент не DocObject, реализация по умолчанию вызывает [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen). Если вы хотите выполнить специальная обработка при открытии элемента DocObject переопределите эту функцию.  
  
## <a name="see-also"></a>См. также  
 [Класса, производного от COleServerItem](../../mfc/reference/coleserveritem-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md)   
 [Класс COleDocObjectItem](../../mfc/reference/coledocobjectitem-class.md)

