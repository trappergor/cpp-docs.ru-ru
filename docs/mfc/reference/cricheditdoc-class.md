---
title: "CRichEditDoc-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditDoc
dev_langs:
- C++
helpviewer_keywords:
- document/view architecture, rich edit controls
- OLE containers, rich edit
- documents, rich edit
- rich edit controls, OLE container
- CRichEditDoc class
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c7233c27c92c6dc689853e1913bb26f0bb5941fa
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditdoc-class"></a>CRichEditDoc-класс
С [CRichEditView](../../mfc/reference/cricheditview-class.md) и [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), предоставляет функциональные возможности управления "rich edit" в контексте архитектуры представления документов MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CRichEditDoc : public COleServerDoc  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRichEditDoc::CreateClientItem](#createclientitem)|Вызывается для выполнения очистки документа.|  
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|Указывает, следует ли включать сведения о форматировании потока входных и выходных данных.|  
|[CRichEditDoc::GetView](#getview)|Извлекает asssociated [CRichEditView](../../mfc/reference/cricheditview-class.md) объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRichEditDoc::m_bRTF](#m_brtf)|Указывает, должен ли поток ввода-вывода включать форматирование.|  
  
## <a name="remarks"></a>Примечания  
 «Управления rich edit» — это окно, в котором пользователь может вводить и редактировать текст. Текст можно назначить форматирование знаков и абзацев и может включать внедренные объекты OLE. Элементы управления rich edit предоставляют программный интерфейс для форматирования текста. Тем не менее приложение должно реализовать все компоненты пользовательского интерфейса, необходимые для предоставления пользователю операций форматирования.  
  
 `CRichEditView`Сохраняет текст и параметры форматирования текста. `CRichEditDoc`хранит список клиентских элементов в представлении. `CRichEditCntrItem`предоставляет доступ стороне контейнера для элементов OLE клиента.  
  
 Это Windows стандартного элемента управления (и, следовательно, [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) и связанными классами) доступны только для программы под управлением версий Windows 95/98 и Windows NT 3.51 и более поздних версий.  
  
 Пример использования форматируемого документа в приложении MFC, см. [WORDPAD](../../visual-cpp-samples.md) образец приложения.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)  
  
 `CRichEditDoc`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrich.h  
  
##  <a name="a-namecreateclientitema--cricheditdoccreateclientitem"></a><a name="createclientitem"></a>CRichEditDoc::CreateClientItem  
 Эта функция вызывается для создания `CRichEditCntrItem` и добавьте его в этом документе.  
  
```  
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 *preo*  
 Указатель на [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) структуру, которая описывает элемент OLE. Новый `CRichEditCntrItem` объекта создается вокруг этого элемента OLE. Если *preo* — **NULL**, новый элемент клиента является пустым.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новый указатель [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) объекта, который был добавлен к этому документу.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не выполняет инициализацию OLE.  
  
 Дополнительные сведения см. в разделе [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetstreamformata--cricheditdocgetstreamformat"></a><a name="getstreamformat"></a>CRichEditDoc::GetStreamFormat  
 Эта функция вызывается для определения формата для потоковой передачи содержимого форматируемого текста.  
  
```  
int GetStreamFormat() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из следующих флагов:  
  
- `SF_TEXT`Указывает, что элемент управления форматированием не хранит сведения о форматировании.  
  
- `SF_RTF`Указывает, что элемент управления форматированием сохранять сведения о форматировании.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение зависит от [m_bRTF](#m_brtf) данные-член. Эта функция возвращает `SF_RTF` Если `m_bRTF` — **TRUE**; в противном случае — `SF_TEXT`.  
  
##  <a name="a-namegetviewa--cricheditdocgetview"></a><a name="getview"></a>CRichEditDoc::GetView  
 Эта функция вызывается для доступа к [CRichEditView](../../mfc/reference/cricheditview-class.md) объект, связанный с этим `CRichEditDoc` объекта.  
  
```  
virtual CRichEditView* GetView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CRichEditView` объект, связанный с документом.  
  
### <a name="remarks"></a>Примечания  
 Текст и сведения о форматировании находятся внутри `CRichEditView` объекта. `CRichEditDoc` Поддерживает объект OLE-элементы для сериализации. Должен быть только один `CRichEditView` для каждого `CRichEditDoc`.  
  
##  <a name="a-namembrtfa--cricheditdocmbrtf"></a><a name="m_brtf"></a>CRichEditDoc::m_bRTF  
 Когда **TRUE**, указывает, что [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) и [CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) следует хранить характеристики форматирование знаков и абзацев.  
  
```  
BOOL m_bRTF;  
```  
  
## <a name="see-also"></a>См. также  
 [Пример MFC WORDPAD](../../visual-cpp-samples.md)   
 [Класс COleServerDoc](../../mfc/reference/coleserverdoc-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CRichEditView-класс](../../mfc/reference/cricheditview-class.md)   
 [Класс CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)   
 [Класс COleDocument](../../mfc/reference/coledocument-class.md)   
 [CRichEditCtrl-класс](../../mfc/reference/cricheditctrl-class.md)

