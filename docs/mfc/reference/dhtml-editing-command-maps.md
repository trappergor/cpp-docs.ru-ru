---
title: Схемы команд редактирования DHTML
ms.date: 11/04/2016
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
ms.openlocfilehash: 62b388eb178be018655ea2b2be00d7321da50335
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365822"
---
# <a name="dhtml-editing-command-maps"></a>Схемы команд редактирования DHTML

Следующие макросы можно использовать для картирования команд редактирования DHTML в классах [CHtmlEditView.](../../mfc/reference/chtmleditview-class.md) Пример их использования можно ознакомьтесь [с HTMLEdit Sample](../../overview/visual-cpp-samples.md).

### <a name="dhtml-editing-command-map-macros"></a>DHTML Редактирование Команда Карта Макрос

|||
|-|-|
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|Объявляет командную карту редактирования DHTML в классе.|
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|Начинается определение командной карты Редактирования DHTML в классе.|
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|Отметка конец карты команды редактирования DHTML.|
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|Карты идентификатора команды в команду редактирования HTML.|
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|Карты идентификатора команды в команду HTML редактирования и обработчик сообщений.|
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|Карты идентификатора команды к команде редактирования HTML и элементу пользовательского интерфейса.|
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|Отображает идентификатор команды в команду редактирования HTML, обработчик сообщений и элемент пользовательского интерфейса.|

## <a name="declare_dhtmlediting_cmdmap"></a><a name="declare_dhtmlediting_cmdmap"></a>DECLARE_DHTMLEDITING_CMDMAP

Объявляет командную карту редактирования DHTML в классе.

```
DECLARE_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>Параметры

*Classname*<br/>
Имя класса.

### <a name="remarks"></a>Remarks

Этот макрос должен использоваться в определении классов [CHtmlEditView.](../../mfc/reference/chtmleditview-class.md)

Используйте [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap) для реализации карты.

### <a name="example"></a>Пример

Смотрите [HTMLEdit Образец](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

## <a name="begin_dhtmlediting_cmdmap"></a><a name="begin_dhtmlediting_cmdmap"></a>BEGIN_DHTMLEDITING_CMDMAP

Начинается определение командной карты Редактирования DHTML в классе.

```
BEGIN_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>Параметры

*Classname*<br/>
Название класса, содержащее командную карту редактирования DHTML. Этот класс должен прямо или косвенно вытекать из [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) и включать [DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap) макрос в свое определение класса.

### <a name="remarks"></a>Remarks

Добавьте в класс карту команды редактирования DHTML для картирования команд пользовательского интерфейса в команды для редактирования HTML.

Поместите BEGIN_DHTMLEDITING_CMDMAP макрос в файл реализации класса (.cpp), а затем [DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry) макросов для команд, которые класс должен сопоставить (например, от ID_EDIT_CUT до IDM_CUT). Используйте [END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap) макрос, чтобы отметить конец карты событий.

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

## <a name="end_dhtmlediting_cmdmap"></a><a name="end_dhtmlediting_cmdmap"></a>END_DHTMLEDITING_CMDMAP

Отметка конец карты команды редактирования DHTML.

```
END_DHTMLEDITING_CMDMAP()
```

### <a name="remarks"></a>Remarks

Используйте в сочетании с [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap).

### <a name="example"></a>Пример

Смотрите [HTMLEdit Образец](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

## <a name="dhtmlediting_cmd_entry"></a><a name="dhtmlediting_cmd_entry"></a>DHTMLEDITING_CMD_ENTRY

Карты идентификатора команды в команду редактирования HTML.

```
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды (например, ID_EDIT_COPY).

*dhtmlcmdID*<br/>
Команда редактирования HTML, к которой *карты cmdID* (например, IDM_COPY).

### <a name="example"></a>Пример

Смотрите [HTMLEdit Образец](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

## <a name="dhtmlediting_cmd_entry_func"></a><a name="dhtmlediting_cmd_entry_func"></a>DHTMLEDITING_CMD_ENTRY_FUNC

Карты идентификатора команды в команду HTML редактирования и обработчик сообщений.

```
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды (например, ID_EDIT_COPY).

*dhtmlcmdID*<br/>
Команда редактирования HTML, к которой *карты cmdID* (например, IDM_COPY).

*member_func_name*<br/>
Имя функции обработчика сообщений, к которой отображается команда.

### <a name="example"></a>Пример

Смотрите [HTMLEdit Образец](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

## <a name="dhtmlediting_cmd_entry_type"></a><a name="dhtmlediting_cmd_entry_type"></a>DHTMLEDITING_CMD_ENTRY_TYPE

Карты идентификатора команды к команде редактирования HTML и элементу пользовательского интерфейса.

```
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды (например, ID_EDIT_COPY).

*dhtmlcmdID*<br/>
Команда редактирования HTML, к которой *карты cmdID* (например, IDM_COPY).

*elemType*<br/>
Тип элемента пользовательского интерфейса; один из AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX или AFX_UI_ELEMTYPE_RADIO.

### <a name="example"></a>Пример

Смотрите [HTMLEdit Образец](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

## <a name="dhtmlediting_cmd_entry_func_type"></a><a name="dhtmlediting_cmd_entry_func_type"></a>DHTMLEDITING_CMD_ENTRY_FUNC_TYPE

Отображает идентификатор команды в команду редактирования HTML, обработчик сообщений и элемент пользовательского интерфейса.

```
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды (например, ID_EDIT_COPY).

*dhtmlcmdID*<br/>
Команда редактирования HTML, к которой *карты cmdID* (например, IDM_COPY).

*member_func_name*<br/>
Имя функции обработчика сообщений, к которой отображается команда.

*elemType*<br/>
Тип элемента пользовательского интерфейса; один из AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX или AFX_UI_ELEMTYPE_RADIO.

### <a name="example"></a>Пример

Смотрите [HTMLEdit Образец](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
