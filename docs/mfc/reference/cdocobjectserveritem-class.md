---
title: Класс CDocObjectServerItem
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
ms.openlocfilehash: 66ff2326cd3d08b3f6c8399d7e948d6aab5074c3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391157"
---
# <a name="cdocobjectserveritem-class"></a>Класс CDocObjectServerItem

Реализует команды OLE-сервера специально для серверов DocObject.

## <a name="syntax"></a>Синтаксис

```
class CDocObjectServerItem : public COleServerItem
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|name|Описание|
|----------|-----------------|
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|Создает объект `CDocObjectServerItem`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CDocObjectServerItem::GetDocument](#getdocument)|Извлекает указатель на документ, который содержит элемент.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[CDocObjectServerItem::OnDoVerb](#ondoverb)|Вызывается для выполнения команды.|
|[CDocObjectServerItem::OnHide](#onhide)|Создает исключение, если платформа пытается скрыть элемент DocObject.|
|[CDocObjectServerItem::OnShow](#onshow)|Вызывается платформой, чтобы сделать DocObject элемента на месте active. Если элемент не DocObject, вызывает [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow).|

## <a name="remarks"></a>Примечания

`CDocObjectServerItem` Определяет функции является переопределяемым элементом: [OnHide](#onhide), [OnDoVerb](#ondoverb), and [OnShow](#onshow).

Для использования `CDocObjectServerItem`, убедиться, что [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) в переопределите вашей `COleServerDoc`-производном классе возвращает новый `CDocObjectServerItem` объекта. Если вам нужно изменить функциональные возможности элемента, можно создать новый экземпляр собственного `CDocObjectServerItem`-производного класса.

Дополнительные сведения о DocObjects см. в разделе [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) и [COleCmdUI](../../mfc/reference/colecmdui-class.md) в *Справочник по библиотеке MFC*.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleServerItem](../../mfc/reference/coleserveritem-class.md)

`CDocObjectServerItem`

## <a name="requirements"></a>Требования

**Заголовок:** afxdocob.h

##  <a name="cdocobjectserveritem"></a>  CDocObjectServerItem::CDocObjectServerItem

Создает объект `CDocObjectServerItem`.

```
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```

### <a name="parameters"></a>Параметры

*pServerDoc*<br/>
Указатель на документ, который будет содержать новый элемент DocObject.

*bAutoDelete*<br/>
Указывает, может ли быть удален объект при отпускании ссылку на него. Установите значение FALSE, если аргумент `CDocObjectServerItem` объект является неотъемлемой частью данных документа. Задано значение TRUE, если объект является вторичной структура, используемая для определения диапазона в данных документа, которые могут удаляться платформой.

##  <a name="getdocument"></a>  CDocObjectServerItem::GetDocument

Извлекает указатель на документ, который содержит элемент.

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на документ, который содержит элемент; Значение NULL, если элемент не является частью документа.

### <a name="remarks"></a>Примечания

Это позволяет доступ к документу сервера, который передается в качестве аргумента для [CDocObjectServerItem](#cdocobjectserveritem) конструктор.

##  <a name="ondoverb"></a>  CDocObjectServerItem::OnDoVerb

Вызывается платформой для выполнения указанной команды.

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>Параметры

*iVerb*<br/>
Указывает команду для выполнения. Возможные значения см. в разделе [функция IOleObject::DoVerb](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) в пакете Windows SDK.

### <a name="remarks"></a>Примечания

По умолчанию реализация вызывает [OnShow](#onshow) функция-член, если элемент является DocObject и указан OLEIVERB_INPLACEACTIVATE или OLEIVERB_SHOW. Если элемент не DocObject или указан другой команды, по умолчанию реализация вызывает [COleServerItem::OnDoVerb](../../mfc/reference/coleserveritem-class.md#ondoverb).

##  <a name="onhide"></a>  CDocObjectServerItem::OnHide

Вызвано структурой для скрытия элемента.

```
virtual void OnHide();
```

### <a name="remarks"></a>Примечания

Реализация по умолчанию вызывает исключение, если элемент является DocObject. Не удается скрыть active DocObject элемент, так как она использует представление целиком. Необходимо отключить элемент DocObject, чтобы убрать его. Если элемент не DocObject, реализация по умолчанию вызывает [COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide).

##  <a name="onshow"></a>  CDocObjectServerItem::OnShow

Вызывается платформой для указания серверное приложение, чтобы сделать DocObject элемента на месте active.

```
virtual void OnShow();
```

### <a name="remarks"></a>Примечания

Если элемент не DocObject, реализация по умолчанию вызывает [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen). Переопределите эту функцию, если вы хотите выполнить специальная обработка при открытии элемента DocObject.

## <a name="see-also"></a>См. также

[Класс COleServerItem](../../mfc/reference/coleserveritem-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md)<br/>
[Класс COleDocObjectItem](../../mfc/reference/coledocobjectitem-class.md)
