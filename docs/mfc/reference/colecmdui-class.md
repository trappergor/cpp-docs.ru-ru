---
title: Класс COleCmdUI
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
ms.openlocfilehash: 1b7a6b21a3ad778b4a5ca345b1aaf42875810e4e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376270"
---
# <a name="colecmdui-class"></a>Класс COleCmdUI

Реализует метод для MFC, позволяющий обновлять состояние объектов ИП, связанных с зависимыми от `IOleCommandTarget`функциями вашего приложения.

## <a name="syntax"></a>Синтаксис

```
class COleCmdUI : public CCmdUI
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeCmdUI::COleCmdUI](#colecmdui)|Формирует объект `COleCmdUI`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleCmdUI::Включить](#enable)|Устанавливает или очищает флаг команды включить.|
|[ColeCmdUI:SetCheck](#setcheck)|Устанавливает состояние команды переключения/выключения.|
|[COleCmdUI::SetText](#settext)|Возвращает имя текста или строку состояния для команды.|

## <a name="remarks"></a>Remarks

В приложении, которое не включено для DocObjects, когда пользователь просматривает меню в приложении, MFC обрабатывает UPDATE_COMMAND_UI уведомлений. Каждому уведомлению дается объект [CCmdUI,](../../mfc/reference/ccmdui-class.md) которым можно манипулировать, чтобы отразить состояние конкретной команды. Однако, когда приложение включено для DocObjects, MFC `COleCmdUI` обрабатывает UPDATE_OLE_COMMAND_UI уведомления и назначает объекты.

`COleCmdUI`позволяет DocObject получать команды, которые возникают в пользовательском интерфейсе контейнера (например, FileNew, Open, Print и так далее), и позволяет контейнеру получать команды, которые происходят в пользовательском интерфейсе DocObject. Хотя `IDispatch` может быть использован для отправки тех же команд, `IOleCommandTarget` обеспечивает более простой способ запроса и выполнения, поскольку он опирается на стандартный набор команд, как правило, без аргументов, и никакой тип информации участвует. `COleCmdUI`может использоваться для включения, обновления и установки других свойств команд пользовательского интерфейса DocObject. Если вы хотите вызвать команду, позвоните [cOleServerDoc::OnExecOleCmd](../../mfc/reference/coleserverdoc-class.md#onexecolecmd).

Для получения дополнительной информации о DocObjects, [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)см. [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CCmdUI](../../mfc/reference/ccmdui-class.md)

`COleCmdUI`

## <a name="requirements"></a>Требования

**Заголовок:** afxdocobj.h

## <a name="colecmduicolecmdui"></a><a name="colecmdui"></a>ColeCmdUI::COleCmdUI

Строит объект, связанный `COleCmdUI` с определенной командой пользовательского интерфейса.

```
COleCmdUI(
    OLECMD* rgCmds,
    ULONG cCmds,
    const GUID* m_pGroup);
```

### <a name="parameters"></a>Параметры

*rgCmds*<br/>
Список поддерживаемых команд, связанных с данным GUID. Структура `OLECMD` связывает команды с флагами команд.

*cCmds*<br/>
Количество команд в *rgCmds*.

*pGroup*<br/>
Указатель на GUID, который определяет набор команд.

### <a name="remarks"></a>Remarks

Объект `COleCmdUI` предоставляет программный интерфейс для обновления объектов пользовательского интерфейса DocObject, таких как пункты меню или кнопки управления барами. Объекты пользователь-интерфейса могут быть включены, отключены, `COleCmdUI` проверены и/или очищены через объект.

## <a name="colecmduienable"></a><a name="enable"></a>COleCmdUI::Включить

Вызовите эту функцию, `COleCmdUI` чтобы установить флаг команды объекта на OLECOMDF_ENABLED, который говорит интерфейсу команда доступна и включена, или очистить флаг команды.

```
virtual void Enable(BOOL bOn);
```

### <a name="parameters"></a>Параметры

*Бон*<br/>
Указывает, должна ли `COleCmdUI` быть включена или отключена команда, связанная с объектом. Nonzero позволяет командовать; 0 отскакивает от команды.

## <a name="colecmduisetcheck"></a><a name="setcheck"></a>ColeCmdUI:SetCheck

Вызов ими функции для настройки состояния команды переключения., выключенной.

```
virtual void SetCheck(int nCheck);
```

### <a name="parameters"></a>Параметры

*Nпроверьте*<br/>
Значение, определяющее состояние для установки команды переключения/выключения. Возможны следующие значения.

|Значение|Описание|
|-----------|-----------------|
|**1**|Устанавливает команду на.|
|**2**|Устанавливает команду на неопределенный; состояние не может быть определено, поскольку атрибут этой команды находится как в состоянии, так и вне его в соответствующем выборе.|
|любое другое значение|Устанавливает команду, чтобы выключить.|

## <a name="colecmduisettext"></a><a name="settext"></a>COleCmdUI::SetText

Вызовите эту функцию, чтобы вернуть имя текста или строку состояния для команды.

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Указатель на текст, который будет использоваться с командой.

## <a name="see-also"></a>См. также раздел

[Класс CCmdUI](../../mfc/reference/ccmdui-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
