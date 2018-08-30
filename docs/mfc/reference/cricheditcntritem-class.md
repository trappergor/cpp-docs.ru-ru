---
title: Класс CRichEditCntrItem | Документация Майкрософт
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
ms.openlocfilehash: 17f50f5e4fb8b9330a09d4964aa99fbf01f4b34d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43206975"
---
# <a name="cricheditcntritem-class"></a>Класс CRichEditCntrItem
С помощью [CRichEditView](../../mfc/reference/cricheditview-class.md) и [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), предоставляет функции элемента управления форматированным редактированием в контексте архитектуры представлений документов MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CRichEditCntrItem : public COleClientItem  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CRichEditCntrItem::CRichEditCntrItem](#cricheditcntritem)|Создает объект `CRichEditCntrItem`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CRichEditCntrItem::SyncToRichEditObject](#synctoricheditobject)|Активирует элемент другого типа.|  
  
## <a name="remarks"></a>Примечания  
 Управления rich edit «» — это окно, в котором пользователь может вводить и редактировать текст. Текст можно назначить форматированием символов и абзацев и могут включать внедренные объекты OLE. Элементы управления rich edit предоставляют программный интерфейс для форматирования текста. Тем не менее приложение должно реализовать все компоненты пользовательского интерфейса, необходимые для предоставления пользователю операций форматирования.  
  
 `CRichEditView` хранит текст и параметры форматирования текста. `CRichEditDoc` ведет список OLE клиентские элементы, которые находятся в представлении. `CRichEditCntrItem` предоставляет доступ со стороны контейнера к элемент клиента OLE.  
  
 Это Windows общего элемента управления (и, следовательно, [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) и связанными классами) доступны только для программ, работающих в версиях Windows 95/98 и Windows NT 3.51 и более поздних версиях.  
  
 Пример использования элементов контейнера форматированным редактированием в приложении MFC, см. в разделе [WORDPAD](../../visual-cpp-samples.md) пример приложения.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrich.h  
  
##  <a name="cricheditcntritem"></a>  CRichEditCntrItem::CRichEditCntrItem  
 Вызывайте эту функцию для создания `CRichEditCntrItem` объекта и его добавления в документе-контейнере.  
  
```  
CRichEditCntrItem(
    REOBJECT* preo = NULL,  
    CRichEditDoc* pContainer = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *preo*  
 Указатель на [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) структуры, который описывает объект OLE. Новый `CRichEditCntrItem` создается вокруг этого элемента OLE. Если *preo* имеет значение NULL, элемент клиента является пустым.  
  
 *pContainer*  
 Указатель на документ контейнера, который будет содержать данный элемент. Если *pContainer* имеет значение NULL, необходимо явно вызывать [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem) добавить этот элемент клиента в документ.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не выполняет инициализацию OLE.  
  
 Дополнительные сведения см. в разделе [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) структуры в пакете Windows SDK.  
  
##  <a name="synctoricheditobject"></a>  CRichEditCntrItem::SyncToRichEditObject  
 Вызывайте эту функцию для синхронизации аспект устройства, [DVASPECT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect), это `CRichEditCntrltem` значению, указанному *reo*.  
  
```  
void SyncToRichEditObject(REOBJECT& reo);
```  
  
### <a name="parameters"></a>Параметры  
 *reo*  
 Ссылка на [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) структуры, который описывает объект OLE.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [DVASPECT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect) в пакете Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC WORDPAD](../../visual-cpp-samples.md)   
 [Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)   
 [Класс CRichEditView](../../mfc/reference/cricheditview-class.md)
