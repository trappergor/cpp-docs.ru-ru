---
title: Класс Кдокобжектсерверитем
ms.date: 03/27/2019
f1_keywords:
- CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::GetDocument
- AFXDOCOB/CDocObjectServerItem::OnDoVerb
- AFXDOCOB/CDocObjectServerItem::OnHide
- AFXDOCOB/CDocObjectServerItem::OnShow
helpviewer_keywords:
- CDocObjectServerItem [MFC], CDocObjectServerItem
- CDocObjectServerItem [MFC], GetDocument
- CDocObjectServerItem [MFC], OnDoVerb
- CDocObjectServerItem [MFC], OnHide
- CDocObjectServerItem [MFC], OnShow
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
ms.openlocfilehash: 4d44791415626f1a94500b9c3885581d67e8fe42
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506823"
---
# <a name="cdocobjectserveritem-class"></a>Класс Кдокобжектсерверитем

Реализует команды OLE-сервера специально для серверов DocObject.

## <a name="syntax"></a>Синтаксис

```
class CDocObjectServerItem : public COleServerItem
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|name|Описание|
|----------|-----------------|
|[Кдокобжектсерверитем:: Кдокобжектсерверитем](#cdocobjectserveritem)|Создает объект `CDocObjectServerItem`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кдокобжектсерверитем:: a Document](#getdocument)|Извлекает указатель на документ, содержащий элемент.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[CDocObjectServerItem::OnDoVerb](#ondoverb)|Вызывается для выполнения команды.|
|[CDocObjectServerItem::OnHide](#onhide)|Создает исключение, если платформа пытается скрыть элемент DocObject.|
|[Кдокобжектсерверитем:: onShow](#onshow)|Вызывается платформой для того, чтобы элемент DocObject был активен на месте. Если элемент не является DocObject, вызывает [COleServerItem:: onShow](../../mfc/reference/coleserveritem-class.md#onshow).|

## <a name="remarks"></a>Примечания

`CDocObjectServerItem`Определяет переопределяемые функции элементов: [OnHide](#onhide), [Ондоверб](#ondoverb)и [onHide](#onshow).

Чтобы использовать `CDocObjectServerItem`, убедитесь, что переопределение [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) в `COleServerDoc`классе, производном от, `CDocObjectServerItem` возвращает новый объект. Если необходимо изменить какие `CDocObjectServerItem`-либо функции в элементе, можно создать новый экземпляр класса, производного от.

Дополнительные сведения о Докобжектс см. в разделе [кдокобжектсервер](../../mfc/reference/cdocobjectserver-class.md) и [колекмдуи](../../mfc/reference/colecmdui-class.md) в *справочнике по MFC*.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[кдоЦитем](../../mfc/reference/cdocitem-class.md)

[COleServerItem](../../mfc/reference/coleserveritem-class.md)

`CDocObjectServerItem`

## <a name="requirements"></a>Требования

**Заголовок:** афксдокоб. h

##  <a name="cdocobjectserveritem"></a>Кдокобжектсерверитем:: Кдокобжектсерверитем

Создает объект `CDocObjectServerItem`.

```
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```

### <a name="parameters"></a>Параметры

*псервердок*<br/>
Указатель на документ, который будет содержать новый элемент DocObject.

*баутоделете*<br/>
Указывает, можно ли удалить объект при освобождении ссылки на него. Если `CDocObjectServerItem` объект является неотъемлемой частью данных документа, задайте для аргумента значение false. Задайте значение TRUE, если объект является вторичной структурой, используемой для обнаружения диапазона в данных документа, который может быть удален платформой.

##  <a name="getdocument"></a>Кдокобжектсерверитем:: a Document

Извлекает указатель на документ, содержащий элемент.

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на документ, содержащий элемент; Значение NULL, если элемент не является частью документа.

### <a name="remarks"></a>Примечания

Это позволяет получить доступ к серверному документу, переданному в качестве аргумента в конструктор [кдокобжектсерверитем](#cdocobjectserveritem) .

##  <a name="ondoverb"></a>  CDocObjectServerItem::OnDoVerb

Вызывается платформой для выполнения указанной команды.

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>Параметры

*иверб*<br/>
Задает выполняемую команду. Возможные значения см. в разделе [иолеобжект::D оверб](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) в Windows SDK.

### <a name="remarks"></a>Примечания

Реализация по умолчанию вызывает функцию [-член](#onshow) OnShow если элемент является DocObject, а параметр OLEIVERB_INPLACEACTIVATE или OLEIVERB_SHOW задан. Если элемент не является DocObject или задан другой глагол, реализация по умолчанию вызывает [COleServerItem:: ондоверб](../../mfc/reference/coleserveritem-class.md#ondoverb).

##  <a name="onhide"></a>  CDocObjectServerItem::OnHide

Вызывается платформой для скрытия элемента.

```
virtual void OnHide();
```

### <a name="remarks"></a>Примечания

Реализация по умолчанию создает исключение, если элемент является DocObject. Нельзя скрыть активный элемент DocObject, так как он занимает все представление. Чтобы убрать элемент DocObject, необходимо отключить его. Если элемент не является DocObject, реализация по умолчанию вызывает [COleServerItem:: onHide](../../mfc/reference/coleserveritem-class.md#onhide).

##  <a name="onshow"></a>Кдокобжектсерверитем:: onShow

Вызывается платформой для указания серверному приложению сделать активным элемент DocObject.

```
virtual void OnShow();
```

### <a name="remarks"></a>Примечания

Если элемент не является DocObject, реализация по умолчанию вызывает [COleServerItem:: onShow](../../mfc/reference/coleserveritem-class.md#onopen). Переопределите эту функцию, если требуется выполнить специальную обработку при открытии элемента DocObject.

## <a name="see-also"></a>См. также

[Класс COleServerItem](../../mfc/reference/coleserveritem-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md)<br/>
[Класс COleDocObjectItem](../../mfc/reference/coledocobjectitem-class.md)
