---
title: Класс CRichEditDoc | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
dev_langs:
- C++
helpviewer_keywords:
- CRichEditDoc [MFC], CreateClientItem
- CRichEditDoc [MFC], GetStreamFormat
- CRichEditDoc [MFC], GetView
- CRichEditDoc [MFC], m_bRTF
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1343b2bffa86f04200e1f8c5451640345c58c73b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420352"
---
# <a name="cricheditdoc-class"></a>Класс CRichEditDoc

С помощью [CRichEditView](../../mfc/reference/cricheditview-class.md) и [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), предоставляет функции элемента управления форматированным редактированием в контексте архитектуры представлений документов MFC.

## <a name="syntax"></a>Синтаксис

```
class CRichEditDoc : public COleServerDoc
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRichEditDoc::CreateClientItem](#createclientitem)|Вызывается, чтобы выполнить очистку документа.|
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|Указывает, следует ли включать сведения о форматировании потока входных и выходных данных.|
|[CRichEditDoc::GetView](#getview)|Извлекает asssociated [CRichEditView](../../mfc/reference/cricheditview-class.md) объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CRichEditDoc::m_bRTF](#m_brtf)|Указывает, должен ли поток ввода-вывода включать форматирование.|

## <a name="remarks"></a>Примечания

Управления rich edit «» — это окно, в котором пользователь может вводить и редактировать текст. Текст можно назначить форматированием символов и абзацев и могут включать внедренные объекты OLE. Элементы управления rich edit предоставляют программный интерфейс для форматирования текста. Тем не менее приложение должно реализовать все компоненты пользовательского интерфейса, необходимые для предоставления пользователю операций форматирования.

`CRichEditView` хранит текст и параметры форматирования текста. `CRichEditDoc` ведет список клиентские элементы, которые находятся в представлении. `CRichEditCntrItem` предоставляет доступ со стороны контейнера к клиентские элементы OLE.

Это Windows общего элемента управления (и, следовательно, [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) и связанными классами) доступны только для программ, работающих в версиях Windows 95/98 и Windows NT 3.51 и более поздних версиях.

Пример использования документа форматированным редактированием в приложении MFC, см. в разделе [WORDPAD](../../visual-cpp-samples.md) пример приложения.

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

##  <a name="createclientitem"></a>  CRichEditDoc::CreateClientItem

Вызывайте эту функцию для создания `CRichEditCntrItem` и добавьте его к этому документу.

```
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;
```

### <a name="parameters"></a>Параметры

*preo*<br/>
Указатель на [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) структуры, который описывает объект OLE. Новый `CRichEditCntrItem` создается вокруг этого элемента OLE. Если *preo* имеет значение NULL, новый элемент клиента является пустым.

### <a name="return-value"></a>Возвращаемое значение

Указатель на новый [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) объект, который был добавлен к этому документу.

### <a name="remarks"></a>Примечания

Эта функция не выполняет инициализацию OLE.

Дополнительные сведения см. в разделе [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) структуры в пакете Windows SDK.

##  <a name="getstreamformat"></a>  CRichEditDoc::GetStreamFormat

Вызывайте эту функцию, чтобы определить формат текста для потоковой передачи содержимого форматированным редактированием.

```
int GetStreamFormat() const;
```

### <a name="return-value"></a>Возвращаемое значение

Один из следующих флагов:

- SF_TEXT указывает, что элемент управления rich edit не сохраняет сведения о форматировании.

- SF_RTF указывает, что элемент управления rich edit поддерживать сведения о форматировании.

### <a name="remarks"></a>Примечания

Возвращаемое значение зависит от [m_bRTF](#m_brtf) данные-член. Эта функция возвращает SF_RTF, если `m_bRTF` имеет значение TRUE; в противном случае — SF_TEXT.

##  <a name="getview"></a>  CRichEditDoc::GetView

Вызывайте эту функцию, чтобы получить доступ к [CRichEditView](../../mfc/reference/cricheditview-class.md) объект, связанный с данным `CRichEditDoc` объекта.

```
virtual CRichEditView* GetView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CRichEditView` объект, связанный с документом.

### <a name="remarks"></a>Примечания

Текст и сведения о форматировании хранятся внутри `CRichEditView` объекта. `CRichEditDoc` Поддерживает элементы OLE для сериализации. Должен быть только один `CRichEditView` для каждого `CRichEditDoc`.

##  <a name="m_brtf"></a>  CRichEditDoc::m_bRTF

Если значение равно TRUE, указывает, что [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) и [CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) следует хранить абзаца и характеристики форматирования символов.

```
BOOL m_bRTF;
```

## <a name="see-also"></a>См. также

[Пример MFC WORDPAD](../../visual-cpp-samples.md)<br/>
[Класс COleServerDoc](../../mfc/reference/coleserverdoc-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CRichEditView](../../mfc/reference/cricheditview-class.md)<br/>
[Класс CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)<br/>
[Класс COleDocument](../../mfc/reference/coledocument-class.md)<br/>
[Класс CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)
