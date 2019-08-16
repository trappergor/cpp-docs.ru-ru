---
title: Класс CRichEditDoc
ms.date: 11/04/2016
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
helpviewer_keywords:
- CRichEditDoc [MFC], CreateClientItem
- CRichEditDoc [MFC], GetStreamFormat
- CRichEditDoc [MFC], GetView
- CRichEditDoc [MFC], m_bRTF
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
ms.openlocfilehash: def0c55ff1faf12729226aa445c9614119c546c4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502677"
---
# <a name="cricheditdoc-class"></a>Класс CRichEditDoc

С помощью [CRichEditView](../../mfc/reference/cricheditview-class.md) и [кричедиткнтритем](../../mfc/reference/cricheditcntritem-class.md)предоставляет функциональные возможности элемента управления Rich Edit в контексте архитектуры представления документов MFC.

## <a name="syntax"></a>Синтаксис

```
class CRichEditDoc : public COleServerDoc
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CRichEditDoc:: Креатеклиентитем](#createclientitem)|Вызывается для выполнения очистки документа.|
|[CRichEditDoc:: Жетстреамформат](#getstreamformat)|Указывает, должны ли входные и выходные данные потоковой передачи включать сведения о форматировании.|
|[CRichEditDoc:: View](#getview)|Извлекает объект [CRichEditView](../../mfc/reference/cricheditview-class.md) асссоЦиатед.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CRichEditDoc:: m_bRTF](#m_brtf)|Указывает, должен ли потоковый ввод-вывод включать форматирование.|

## <a name="remarks"></a>Примечания

«Форматируемый элемент управления» — это окно, в котором пользователь может вводить и редактировать текст. Тексту можно присвоить форматирование символов и абзацев, а также включить внедренные объекты OLE. Элементы управления Rich Edit предоставляют программный интерфейс для форматирования текста. Однако приложение должно реализовывать любые компоненты пользовательского интерфейса, необходимые для того, чтобы сделать операции форматирования доступными для пользователя.

`CRichEditView`поддерживает текстовую характеристику текста и форматирования текста. `CRichEditDoc`поддерживает список клиентских элементов, которые находятся в представлении. `CRichEditCntrItem`предоставляет доступ на стороне контейнера к элементам клиента OLE.

Этот общий элемент управления Windows (и, следовательно, [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) и связанные классы) доступен только для программ, работающих под управлением Windows 95/98 и Windows NT версии 3,51 и более поздних версий.

Пример использования документа с богатыми возможностями редактирования в приложении MFC см. в примере приложения [WordPad](../../overview/visual-cpp-samples.md) .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[коледокумент](../../mfc/reference/coledocument-class.md)

[колелинкингдок](../../mfc/reference/colelinkingdoc-class.md)

[колесервердок](../../mfc/reference/coleserverdoc-class.md)

`CRichEditDoc`

## <a name="requirements"></a>Требования

**Заголовок:** афксрич. h

##  <a name="createclientitem"></a>CRichEditDoc:: Креатеклиентитем

Вызовите эту функцию, чтобы `CRichEditCntrItem` создать объект и добавить его в этот документ.

```
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;
```

### <a name="parameters"></a>Параметры

*прео*<br/>
Указатель на структуру [объекта](/windows/win32/api/richole/ns-richole-reobject) , описывающую элемент OLE. Новый `CRichEditCntrItem` объект создается вокруг этого объекта OLE. Если *прео* имеет значение null, новый элемент клиента пуст.

### <a name="return-value"></a>Возвращаемое значение

Указатель на новый объект [кричедиткнтритем](../../mfc/reference/cricheditcntritem-class.md) , который был добавлен в этот документ.

### <a name="remarks"></a>Примечания

Эта функция не выполняет инициализацию OLE.

Дополнительные сведения см. в описании структуры реобъектного [объекта](/windows/win32/api/richole/ns-richole-reobject) в Windows SDK.

##  <a name="getstreamformat"></a>CRichEditDoc:: Жетстреамформат

Вызовите эту функцию, чтобы определить текстовый формат для потоковой передачи содержимого расширенного редактирования.

```
int GetStreamFormat() const;
```

### <a name="return-value"></a>Возвращаемое значение

Один из следующих флагов:

- SF_TEXT указывает, что элемент управления Rich Edit не поддерживает сведения о форматировании.

- SF_RTF указывает, что форматируемый элемент управления "поле ввода" сохраняет сведения о форматировании.

### <a name="remarks"></a>Примечания

Возвращаемое значение основано на элементе данных [m_bRTF](#m_brtf) . Эта функция возвращает SF_RTF, `m_bRTF` если имеет значение true; в противном случае — SF_TEXT.

##  <a name="getview"></a>CRichEditDoc:: View

Вызовите эту функцию для доступа к объекту [CRichEditView](../../mfc/reference/cricheditview-class.md) , связанному с этим `CRichEditDoc` объектом.

```
virtual CRichEditView* GetView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CRichEditView` , связанный с документом.

### <a name="remarks"></a>Примечания

Сведения о тексте и форматировании содержатся в `CRichEditView` объекте. `CRichEditDoc` Объект поддерживает элементы OLE для сериализации. Для каждого `CRichEditView` `CRichEditDoc`из них должно быть только одно.

##  <a name="m_brtf"></a>CRichEditDoc:: m_bRTF

Если значение равно TRUE, то указывает, что [CRichEditCtrl:: Streaming](../../mfc/reference/cricheditctrl-class.md#streamin) и [CRichEditCtrl:: Streaming](../../mfc/reference/cricheditctrl-class.md#streamout) должны сохранять характеристики абзаца и форматирования символов.

```
BOOL m_bRTF;
```

## <a name="see-also"></a>См. также

[Образец WORDPAD для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс COleServerDoc](../../mfc/reference/coleserverdoc-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CRichEditView](../../mfc/reference/cricheditview-class.md)<br/>
[Класс CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)<br/>
[Класс COleDocument](../../mfc/reference/coledocument-class.md)<br/>
[Класс CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)
