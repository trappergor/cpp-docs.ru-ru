---
title: Класс Кричедиткнтритем
ms.date: 11/04/2016
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
helpviewer_keywords:
- CRichEditCntrItem [MFC], CRichEditCntrItem
- CRichEditCntrItem [MFC], SyncToRichEditObject
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
ms.openlocfilehash: b333cbbe33b42709614376cf98be01111be967a2
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916812"
---
# <a name="cricheditcntritem-class"></a>Класс Кричедиткнтритем

С помощью [CRichEditView](../../mfc/reference/cricheditview-class.md) и [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)предоставляет функциональные возможности элемента управления Rich Edit в контексте архитектуры представления документов MFC.

## <a name="syntax"></a>Синтаксис

```
class CRichEditCntrItem : public COleClientItem
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кричедиткнтритем:: Кричедиткнтритем](#cricheditcntritem)|Создает объект `CRichEditCntrItem`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кричедиткнтритем:: Синкторичедитобжект](#synctoricheditobject)|Активирует элемент как другой тип.|

## <a name="remarks"></a>Примечания

«Форматируемый элемент управления» — это окно, в котором пользователь может вводить и редактировать текст. Тексту можно присвоить форматирование символов и абзацев, а также включить внедренные объекты OLE. Элементы управления Rich Edit предоставляют программный интерфейс для форматирования текста. Однако приложение должно реализовывать любые компоненты пользовательского интерфейса, необходимые для того, чтобы сделать операции форматирования доступными для пользователя.

`CRichEditView`поддерживает текстовую характеристику текста и форматирования текста. `CRichEditDoc`поддерживает список элементов OLE клиента, которые находятся в представлении. `CRichEditCntrItem`предоставляет доступ на стороне контейнера к элементу OLE-клиента.

Этот общий элемент управления Windows (и, следовательно, [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) и связанные классы) доступен только для программ, работающих под управлением Windows 95/98 и Windows NT версии 3,51 и более поздних версий.

Пример использования элементов контейнера с богатыми возможностями редактирования в приложении MFC см. в примере приложения [WordPad](../../overview/visual-cpp-samples.md) .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[кдоЦитем](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`CRichEditCntrItem`

## <a name="requirements"></a>Требования

**Заголовок:** афксрич. h

##  <a name="cricheditcntritem"></a>Кричедиткнтритем:: Кричедиткнтритем

Вызовите эту функцию, чтобы `CRichEditCntrItem` создать объект и добавить его в документ-контейнер.

```
CRichEditCntrItem(
    REOBJECT* preo = NULL,
    CRichEditDoc* pContainer = NULL);
```

### <a name="parameters"></a>Параметры

*прео*<br/>
Указатель на структуру [объекта](/windows/desktop/api/richole/ns-richole-reobject) , описывающую элемент OLE. Новый `CRichEditCntrItem` объект создается вокруг этого объекта OLE. Если *прео* имеет значение null, то элемент клиента пуст.

*Pcontainer может*<br/>
Указатель на документ контейнера, который будет содержать этот элемент. Если *pcontainer может* имеет значение null, необходимо явно вызвать [Коледокумент:: AddItem](../../mfc/reference/coledocument-class.md#additem) , чтобы добавить этот клиентский элемент в документ.

### <a name="remarks"></a>Примечания

Эта функция не выполняет инициализацию OLE.

Дополнительные сведения см. в описании структуры реобъектного [объекта](/windows/desktop/api/richole/ns-richole-reobject) в Windows SDK.

##  <a name="synctoricheditobject"></a>Кричедиткнтритем:: Синкторичедитобжект

Вызовите эту функцию, чтобы синхронизировать аспект устройства, [дваспект](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect), `CRichEditCntrltem` с указанным *Рео*.

```
void SyncToRichEditObject(REOBJECT& reo);
```

### <a name="parameters"></a>Параметры

*рео*<br/>
Ссылка на структуру [объектов](/windows/desktop/api/richole/ns-richole-reobject) , описывающую элемент OLE.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [дваспект](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect) в Windows SDK.

## <a name="see-also"></a>См. также

[Образец WORDPAD для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)<br/>
[Класс CRichEditView](../../mfc/reference/cricheditview-class.md)
