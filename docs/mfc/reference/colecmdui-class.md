---
title: Класс Колекмдуи
ms.date: 07/24/2020
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
ms.openlocfilehash: c21d9b504656e6bba5ca693e57958743bb1b8309
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233214"
---
# <a name="colecmdui-class"></a>Класс Колекмдуи

Реализует метод для MFC, позволяющий обновлять состояние объектов ИП, связанных с зависимыми от `IOleCommandTarget`функциями вашего приложения.

## <a name="syntax"></a>Синтаксис

```cpp
class COleCmdUI : public CCmdUI
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Колекмдуи:: Колекмдуи](#colecmdui)|Формирует объект `COleCmdUI`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Колекмдуи:: enable](#enable)|Задает или очищает флаг команды Enable.|
|[Колекмдуи:: Сетчекк](#setcheck)|Задает состояние команды переключателя on/off.|
|[Колекмдуи:: SetText](#settext)|Возвращает текстовое имя или строку состояния для команды.|

## <a name="remarks"></a>Remarks

В приложении, которое не включено для Докобжектс, когда пользователь просматривает меню в приложении, MFC обрабатывает UPDATE_COMMAND_UI нотифкатионс. Каждому уведомлению присваивается объект [Поддержка CCmdUI](../../mfc/reference/ccmdui-class.md) , который можно изменять, чтобы отразить состояние определенной команды. Однако если приложение включено для Докобжектс, MFC обрабатывает UPDATE_OLE_COMMAND_UI уведомлений и назначает `COleCmdUI` объекты.

`COleCmdUI`позволяет DocObject принимать команды, происходящие в пользовательском интерфейсе контейнера (например, Филенев, Open, Print и т. д.), и позволяет контейнеру принимать команды, которые происходят в пользовательском интерфейсе DocObject. Хотя `IDispatch` можно использовать для отправки одних и тех же команд, `IOleCommandTarget` предоставляет более простой способ запроса и выполнения, так как он использует стандартный набор команд, обычно без аргументов, и сведения о типе не участвуют. `COleCmdUI`может использоваться для включения, обновления и настройки других свойств команд пользовательского интерфейса DocObject. Если вы хотите вызвать команду, вызовите метод [колесервердок:: онексеколекмд](../../mfc/reference/coleserverdoc-class.md#onexecolecmd).

Дополнительные сведения о Докобжектс см. в разделе [кдокобжектсервер](../../mfc/reference/cdocobjectserver-class.md) и [кдокобжектсерверитем](../../mfc/reference/cdocobjectserveritem-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CCmdUI](../../mfc/reference/ccmdui-class.md)

`COleCmdUI`

## <a name="requirements"></a>Требования

**Заголовок:** афксдокоб. h

## <a name="colecmduicolecmdui"></a><a name="colecmdui"></a>Колекмдуи:: Колекмдуи

Конструирует объект, `COleCmdUI` связанный с определенной командой пользовательского интерфейса.

```cpp
COleCmdUI(
    OLECMD* rgCmds,
    ULONG cCmds,
    const GUID* m_pGroup);
```

### <a name="parameters"></a>Параметры

*ргкмдс*<br/>
Список поддерживаемых команд, связанных с данным идентификатором GUID. `OLECMD`Структура связывает команды с флагами команд.

*ккмдс*<br/>
Число команд в *ргкмдс*.

*пграуп*<br/>
Указатель на идентификатор GUID, определяющий набор команд.

### <a name="remarks"></a>Remarks

`COleCmdUI`Объект предоставляет программный интерфейс для обновления объектов пользовательского интерфейса DocObject, таких как пункты меню или кнопки панели управления. Объекты пользовательского интерфейса можно включать, отключать, проверять и (или) очищать с помощью `COleCmdUI` объекта.

## <a name="colecmduienable"></a><a name="enable"></a>Колекмдуи:: enable

Вызовите эту функцию, чтобы задать `COleCmdUI` для объекта флаг команды для OLECOMDF_ENABLED, который сообщает интерфейсу, что команда доступна и включена, или снимите флаг команды.

```cpp
virtual void Enable(BOOL bOn);
```

### <a name="parameters"></a>Параметры

*Системе*<br/>
Указывает, `COleCmdUI` должна ли быть включена или отключена команда, связанная с объектом. Ненулевое значение включает команду; 0 — отключить команду.

## <a name="colecmduisetcheck"></a><a name="setcheck"></a>Колекмдуи:: Сетчекк

Эта функция вызывается для задания состояния команды переключателя on/off.

```cpp
virtual void SetCheck(int nCheck);
```

### <a name="parameters"></a>Параметры

*nДополнительные*<br/>
Значение, определяющее состояние для задания команды включения или выключения. Доступны следующие значения:

|Значение|Описание:|
|-----------|-----------------|
|**1**|Задает для команды значение ON.|
|**2**|Задает команду как неопределенную; невозможно определить состояние, так как атрибут этой команды находится в состояниях on и Off в соответствующем выделенном фрагменте.|
|любое другое значение|Задает команду OFF.|

## <a name="colecmduisettext"></a><a name="settext"></a>Колекмдуи:: SetText

Вызовите эту функцию, чтобы вернуть текстовое имя или строку состояния для команды.

```cpp
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Указатель на текст, который будет использоваться с командой.

## <a name="see-also"></a>См. также статью

[Класс поддержка CCmdUI](../../mfc/reference/ccmdui-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)
