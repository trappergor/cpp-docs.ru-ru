---
title: COleCmdUI Class
ms.date: 09/12/2018
f1_keywords:
- COleCmdUI
- AFXDOCOBJ/COleCmdUI
- AFXDOCOBJ/COleCmdUI::COleCmdUI
- AFXDOCOBJ/COleCmdUI::Enable
- AFXDOCOBJ/COleCmdUI::SetCheck
- AFXDOCOBJ/COleCmdUI::SetText
helpviewer_keywords:
- COleCmdUI [MFC], COleCmdUI
- COleCmdUI [MFC], Enable
- COleCmdUI [MFC], SetCheck
- COleCmdUI [MFC], SetText
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
ms.openlocfilehash: 5dc4e9504805146a9eff0f5ab937868226e4516e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148514"
---
# <a name="colecmdui-class"></a>COleCmdUI Class

Реализует метод для MFC, позволяющий обновлять состояние объектов ИП, связанных с зависимыми от `IOleCommandTarget`функциями вашего приложения.

## <a name="syntax"></a>Синтаксис

```
class COleCmdUI : public CCmdUI
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[COleCmdUI::COleCmdUI](#colecmdui)|Создает объект `COleCmdUI`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[COleCmdUI::Enable](#enable)|Устанавливает или снимает флаг команды enable.|
|[COleCmdUI::SetCheck](#setcheck)|Задает состояние включения/выключения переключателя команды.|
|[COleCmdUI::SetText](#settext)|Возвращает текстовую строку имени или состоянии для команды.|

## <a name="remarks"></a>Примечания

В приложении, не включена для DocObjects, когда пользовательские представления, в меню в приложении MFC обрабатывает UPDATE_COMMAND_UI уведомлений. Каждое уведомление предоставляется [CCmdUI](../../mfc/reference/ccmdui-class.md) объект, который можно обрабатывать для отражения состояния определенной команды. Тем не менее, при включении приложения для DocObjects MFC обрабатывает уведомления UPDATE_OLE_COMMAND_UI и назначает `COleCmdUI` объектов.

`COleCmdUI` позволяет DocObject для получения команд, поступающих в пользовательском интерфейсе контейнера (например, FileNew, открыть, печать и т. д.), а контейнер для получения команд, поступающих в пользовательском интерфейсе DocObject. Несмотря на то что `IDispatch` может использоваться для отправки те же команды `IOleCommandTarget` предоставляет простой способ запроса и выполнить, так как он использует стандартный набор команд, обычно без аргументов, и сведения о типе не участвует. `COleCmdUI` можно использовать для включения, обновления и задать другие свойства DocObject команд пользовательского интерфейса. Если вы хотите вызвать команду, вызовите [COleServerDoc::OnExecOleCmd](../../mfc/reference/coleserverdoc-class.md#onexecolecmd).

Дополнительные сведения о DocObjects см. в разделе [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) и [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CCmdUI](../../mfc/reference/ccmdui-class.md)

`COleCmdUI`

## <a name="requirements"></a>Требования

**Заголовок:** afxdocobj.h

##  <a name="colecmdui"></a>  COleCmdUI::COleCmdUI

Создает `COleCmdUI` объект, связанный с командой конкретного пользовательского интерфейса.

```
COleCmdUI(
    OLECMD* rgCmds,
    ULONG cCmds,
    const GUID* m_pGroup);
```

### <a name="parameters"></a>Параметры

*rgCmds*<br/>
Список поддерживаемых команд, связанных с заданным идентификатором GUID. `OLECMD` Структуры связывают команд с помощью командной строки.

*cCmds*<br/>
Количество команд в *rgCmds*.

*pGroup*<br/>
Указатель на GUID, который определяет набор команд.

### <a name="remarks"></a>Примечания

`COleCmdUI` Предоставляет программный интерфейс для обновления объектов DocObject пользовательского интерфейса, таких как команды меню или кнопки панели элементов управления. Объекты пользовательского интерфейса может быть включена, отключена, проверки или очищен через `COleCmdUI` объекта.

##  <a name="enable"></a>  COleCmdUI::Enable

Вызывайте эту функцию, чтобы задать флаг команды `COleCmdUI` объекта OLECOMDF_ENABLED, который указывает интерфейс, команда была доступна и включена, или снимите флаг команды.

```
virtual void Enable(BOOL bOn);
```

### <a name="parameters"></a>Параметры

*bOn*<br/>
Указывает, связан ли команда `COleCmdUI` объект должен быть включен или отключен. Ненулевое значение включает команды; 0 — отключает команды.

##  <a name="setcheck"></a>  COleCmdUI::SetCheck

Вызывайте эту функцию для задания состояния включения/выключения переключателя команды.

```
virtual void SetCheck(int nCheck);
```

### <a name="parameters"></a>Параметры

*Проверьте*<br/>
Значение, определяющее состояние требуется установить переключатель включить или выключить команды. Доступны следующие значения:

|Значение|Описание|
|-----------|-----------------|
|**1**|Задает команду включено.|
|**2**|Задает команду, чтобы определено; не удается определить состояние, так как атрибут этой команды выполняется как и отключение состояний в подходящий вариант выбора.|
|любое другое значение|Задает команды задано значение off.|

##  <a name="settext"></a>  COleCmdUI::SetText

Вызывайте эту функцию для возврата строки имени или состоянии текст для команды.

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Указатель на текст, используемый с командой.

## <a name="see-also"></a>См. также

[Класс CCmdUI](../../mfc/reference/ccmdui-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
