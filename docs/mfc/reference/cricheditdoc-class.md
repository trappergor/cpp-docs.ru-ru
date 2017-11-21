---
title: "CRichEditDoc-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
dev_langs: C++
helpviewer_keywords:
- CRichEditDoc [MFC], CreateClientItem
- CRichEditDoc [MFC], GetStreamFormat
- CRichEditDoc [MFC], GetView
- CRichEditDoc [MFC], m_bRTF
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5105a03b4db49eda1c2338cf85414c4bfc0c153d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cricheditdoc-class"></a>CRichEditDoc-класс
С [CRichEditView](../../mfc/reference/cricheditview-class.md) и [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), предоставляет функциональные возможности элемента управления форматированным редактированием в контексте архитектуры представлений документов MFC.  
  
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
 Управления rich edit «» — это окно, в котором пользователь может вводить и редактировать текст. Текст можно назначить форматирование знаков и абзацев и может содержать внедренные объекты OLE. Элементы управления rich edit предоставляют программный интерфейс для форматирования текста. Тем не менее приложение должно реализовать все компоненты пользовательского интерфейса, необходимые для предоставления пользователю операций форматирования.  
  
 `CRichEditView`Сохраняет текст и параметры форматирования текста. `CRichEditDoc`поддерживает список клиентские элементы, которые находятся в представлении. `CRichEditCntrItem`предоставляет доступ стороне контейнера для элементов OLE клиента.  
  
 Это Windows стандартного элемента управления (и, следовательно, [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) и связанные классы) доступен только для программ, под управлением версий Windows 95/98 и Windows NT 3.51 и более поздних.  
  
 Пример использования документа широкие возможности редактирования в приложениях MFC см. в разделе [WORDPAD](../../visual-cpp-samples.md) образец приложения.  
  
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
  
##  <a name="createclientitem"></a>CRichEditDoc::CreateClientItem  
 Эта функция вызывается для создания `CRichEditCntrItem` и добавить его в этот документ.  
  
```  
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 *preo*  
 Указатель на [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) структуру, которая описывает элемент OLE. Новый `CRichEditCntrItem` создается объект вокруг данного элемента OLE. Если *preo* — **NULL**, новый элемент клиента является пустым.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новый [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) объект, который был добавлен в этот документ.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не выполняет инициализацию OLE.  
  
 Дополнительные сведения см. в разделе [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) структуры в Windows SDK.  
  
##  <a name="getstreamformat"></a>CRichEditDoc::GetStreamFormat  
 Эта функция вызывается для определения формата текста для потоковой передачи содержимого форматированным редактированием.  
  
```  
int GetStreamFormat() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из следующих флагов:  
  
- `SF_TEXT`Указывает, что элемент управления форматированием не сохраняет сведения о форматировании.  
  
- `SF_RTF`Указывает, что элемент управления форматированием поддерживать сведения о форматировании.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение зависит от [m_bRTF](#m_brtf) члена данных. Эта функция возвращает `SF_RTF` Если `m_bRTF` — **TRUE**; в противном случае `SF_TEXT`.  
  
##  <a name="getview"></a>CRichEditDoc::GetView  
 Эта функция вызывается для доступа к [CRichEditView](../../mfc/reference/cricheditview-class.md) объекта, связанного с данным `CRichEditDoc` объекта.  
  
```  
virtual CRichEditView* GetView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CRichEditView` объект, связанный с документом.  
  
### <a name="remarks"></a>Примечания  
 Текст и сведения о форматировании содержатся внутри `CRichEditView` объекта. `CRichEditDoc` Сохраняет OLE-элементы для сериализации. Должен быть только один `CRichEditView` для каждого `CRichEditDoc`.  
  
##  <a name="m_brtf"></a>CRichEditDoc::m_bRTF  
 Когда **TRUE**, указывает, что [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) и [CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) следует хранить характеристики форматирование символов и абзацев.  
  
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
 [Класс CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)
