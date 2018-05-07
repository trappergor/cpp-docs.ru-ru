---
title: Класс CRichEditCntrItem | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCntrItem [MFC], CRichEditCntrItem
- CRichEditCntrItem [MFC], SyncToRichEditObject
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a64950bcb0cc931b4528276e85f5d60e3b5cb08
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cricheditcntritem-class"></a>Класс CRichEditCntrItem
С [CRichEditView](../../mfc/reference/cricheditview-class.md) и [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), предоставляет функциональные возможности элемента управления форматированным редактированием в контексте архитектуры представлений документов MFC.  
  
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
 Управления rich edit «» — это окно, в котором пользователь может вводить и редактировать текст. Текст можно назначить форматирование знаков и абзацев и может содержать внедренные объекты OLE. Элементы управления rich edit предоставляют программный интерфейс для форматирования текста. Тем не менее приложение должно реализовать все компоненты пользовательского интерфейса, необходимые для предоставления пользователю операций форматирования.  
  
 `CRichEditView` Сохраняет текст и параметры форматирования текста. `CRichEditDoc` поддерживает список клиентских элементов управления OLE, находящихся в представлении. `CRichEditCntrItem` Предоставляет контейнер стороне доступ к элемент клиента OLE.  
  
 Это Windows стандартного элемента управления (и, следовательно, [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) и связанные классы) доступен только для программ, под управлением версий Windows 95/98 и Windows NT 3.51 и более поздних.  
  
 Пример использования элементов контейнера широкие возможности редактирования в приложениях MFC см. в разделе [WORDPAD](../../visual-cpp-samples.md) образец приложения.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrich.h  
  
##  <a name="cricheditcntritem"></a>  CRichEditCntrItem::CRichEditCntrItem  
 Эта функция вызывается для создания `CRichEditCntrItem` объекта и добавить его в документе-контейнере.  
  
```  
CRichEditCntrItem(
    REOBJECT* preo = NULL,  
    CRichEditDoc* pContainer = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *preo*  
 Указатель на [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) структуру, которая описывает элемент OLE. Новый `CRichEditCntrItem` создается объект вокруг данного элемента OLE. Если *preo* — **NULL**, клиентский элемент пуст.  
  
 `pContainer`  
 Указатель на документ контейнера, который будет содержать этот элемент. Если `pContainer` — **NULL**, необходимо явным образом вызвать [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem) добавить этот элемент клиента в документ.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не выполняет инициализацию OLE.  
  
 Дополнительные сведения см. в разделе [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) структуры в Windows SDK.  
  
##  <a name="synctoricheditobject"></a>  CRichEditCntrItem::SyncToRichEditObject  
 Эта функция вызывается для синхронизации пропорции устройства [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318), это **CRichEditCntrltem** значению, указанному *reo*.  
  
```  
void SyncToRichEditObject(REOBJECT& reo);
```  
  
### <a name="parameters"></a>Параметры  
 *reo*  
 Ссылка на [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) структуру, которая описывает элемент OLE.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC WORDPAD](../../visual-cpp-samples.md)   
 [Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc-класс](../../mfc/reference/cricheditdoc-class.md)   
 [Класс CRichEditView](../../mfc/reference/cricheditview-class.md)
