---
title: "Класс CRichEditCntrItem | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditCntrItem
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCntrItem class
- OLE items, in rich edit views
- rich edit controls, using
- rich edit controls, OLE items
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
caps.latest.revision: 24
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b29c7c3b80d24ef9ddb94e09c6b5c7bf2444bb4f
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditcntritem-class"></a>Класс CRichEditCntrItem
С [CRichEditView](../../mfc/reference/cricheditview-class.md) и [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), предоставляет функциональные возможности управления "rich edit" в контексте архитектуры представления документов MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CRichEditCntrItem : public COleClientItem  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRichEditCntrItem::CRichEditCntrItem](#cricheditcntritem)|Создает объект `CRichEditCntrItem`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRichEditCntrItem::SyncToRichEditObject](#synctoricheditobject)|Активирует элемент другого типа.|  
  
## <a name="remarks"></a>Примечания  
 «Управления rich edit» — это окно, в котором пользователь может вводить и редактировать текст. Текст можно назначить форматирование знаков и абзацев и может включать внедренные объекты OLE. Элементы управления rich edit предоставляют программный интерфейс для форматирования текста. Тем не менее приложение должно реализовать все компоненты пользовательского интерфейса, необходимые для предоставления пользователю операций форматирования.  
  
 `CRichEditView`Сохраняет текст и параметры форматирования текста. `CRichEditDoc`поддерживает список клиентских элементов управления OLE, находящиеся в представлении. `CRichEditCntrItem`предоставляет доступ стороне контейнера для клиентского объекта OLE.  
  
 Это Windows стандартного элемента управления (и, следовательно, [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) и связанными классами) доступны только для программы под управлением версий Windows 95/98 и Windows NT 3.51 и более поздних версий.  
  
 Пример использования форматируемого контейнер элементов в приложении MFC, в разделе [WORDPAD](../../visual-cpp-samples.md) образец приложения.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrich.h  
  
##  <a name="a-namecricheditcntritema--cricheditcntritemcricheditcntritem"></a><a name="cricheditcntritem"></a>CRichEditCntrItem::CRichEditCntrItem  
 Эта функция вызывается для создания `CRichEditCntrItem` объекта и добавить его в документе-контейнере.  
  
```  
CRichEditCntrItem(
    REOBJECT* preo = NULL,  
    CRichEditDoc* pContainer = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *preo*  
 Указатель на [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) структуру, которая описывает элемент OLE. Новый `CRichEditCntrItem` объекта создается вокруг этого элемента OLE. Если *preo* — **NULL**, клиентский элемент пуст.  
  
 `pContainer`  
 Указатель контейнера документа, содержащего этот элемент. Если `pContainer` — **NULL**, необходимо явно вызвать [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem) добавить этот элемент клиента в документ.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не выполняет инициализацию OLE.  
  
 Дополнительные сведения см. в разделе [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesynctoricheditobjecta--cricheditcntritemsynctoricheditobject"></a><a name="synctoricheditobject"></a>CRichEditCntrItem::SyncToRichEditObject  
 Эта функция вызывается для синхронизации аспект устройства, [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318), это **CRichEditCntrltem** значению, указанному *reo*.  
  
```  
void SyncToRichEditObject(REOBJECT& reo);
```  
  
### <a name="parameters"></a>Параметры  
 *reo*  
 Ссылка на [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) структуру, которая описывает элемент OLE.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Пример MFC WORDPAD](../../visual-cpp-samples.md)   
 [Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc-класс](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditView-класс](../../mfc/reference/cricheditview-class.md)

