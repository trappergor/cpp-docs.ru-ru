---
title: Схемы команд редактирования DHTML
ms.date: 11/04/2016
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
ms.openlocfilehash: 7f420619983283c225ca8fca23c5ea349def1d1b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323064"
---
# <a name="dhtml-editing-command-maps"></a>Схемы команд редактирования DHTML

Следующие макросы можно использовать для сопоставления команд редактирования DHTML [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-производные классы. Пример их использования, см. в разделе [HTMLEdit пример](../../overview/visual-cpp-samples.md).

### <a name="dhtml-editing-command-map-macros"></a>Макросы схемы команд редактирования DHTML

|||
|-|-|
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|Объявляет карты команд редактирования DHTML в классе.|
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|Начинается определение сопоставления команд редактирования DHTML в пределах класса.|
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|Помечает конец карты команд редактирования DHTML.|
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|Сопоставляет идентификатор команды для команды редактирования HTML.|
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|Сопоставляет идентификатор команды для команды редактирования HTML и обработчик сообщений.|
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|Сопоставляет идентификатор команды для команды редактирования HTML и элемент пользовательского интерфейса.|
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|Сопоставляет идентификатор команды редактирования командой, обработчик сообщений и элемент пользовательского интерфейса HTML.|

##  <a name="declare_dhtmlediting_cmdmap"></a>  DECLARE_DHTMLEDITING_CMDMAP

Объявляет карты команд редактирования DHTML в классе.

```
DECLARE_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя класса.

### <a name="remarks"></a>Примечания

Этот макрос будет использоваться в определении [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-производные классы.

Используйте [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap) для реализации карты.

### <a name="example"></a>Пример

См. в разделе [HTMLEdit пример](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

##  <a name="begin_dhtmlediting_cmdmap"></a>  BEGIN_DHTMLEDITING_CMDMAP

Начинается определение сопоставления команд редактирования DHTML в пределах класса.

```
BEGIN_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя класса, содержащего карту команд редактирования DHTML. Этот класс должен прямо или косвенно наследующие от [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) и включают [DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap) макрос в соответствии с определением класса.

### <a name="remarks"></a>Примечания

Добавление карты команд редактирования DHTML класса для сопоставления команд пользовательского интерфейса команды редактирования HTML.

Поместите begin_dhtmlediting_cmdmap-макрос в файле реализации (CPP) класса, за которым следует [DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry) макросы для команд, класс является для сопоставления (например, из ID_EDIT_CUT для IDM_CUT). Используйте [END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap) макрос для обозначения конца набора карты событий.

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

##  <a name="end_dhtmlediting_cmdmap"></a>  END_DHTMLEDITING_CMDMAP

Помечает конец карты команд редактирования DHTML.

```
END_DHTMLEDITING_CMDMAP()
```

### <a name="remarks"></a>Примечания

Использовать в сочетании с [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap).

### <a name="example"></a>Пример

См. в разделе [HTMLEdit пример](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

##  <a name="dhtmlediting_cmd_entry"></a>  DHTMLEDITING_CMD_ENTRY

Сопоставляет идентификатор команды для команды редактирования HTML.

```
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды (например, ID_EDIT_COPY).

*dhtmlcmdID*<br/>
HTML, команда, к которому изменения *cmdID* сопоставляет (например, IDM_COPY).

### <a name="example"></a>Пример

См. в разделе [HTMLEdit пример](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

##  <a name="dhtmlediting_cmd_entry_func"></a>  DHTMLEDITING_CMD_ENTRY_FUNC

Сопоставляет идентификатор команды для команды редактирования HTML и обработчик сообщений.

```
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды (например, ID_EDIT_COPY).

*dhtmlcmdID*<br/>
HTML, команда, к которому изменения *cmdID* сопоставляет (например, IDM_COPY).

*member_func_name*<br/>
Имя функции обработчика сообщений, с которым сопоставляется команды.

### <a name="example"></a>Пример

См. в разделе [HTMLEdit пример](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

##  <a name="dhtmlediting_cmd_entry_type"></a>  DHTMLEDITING_CMD_ENTRY_TYPE

Сопоставляет идентификатор команды для команды редактирования HTML и элемент пользовательского интерфейса.

```
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды (например, ID_EDIT_COPY).

*dhtmlcmdID*<br/>
HTML, команда, к которому изменения *cmdID* сопоставляет (например, IDM_COPY).

*elemType*<br/>
Тип элемента пользовательского интерфейса; одно из AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX или AFX_UI_ELEMTYPE_RADIO.

### <a name="example"></a>Пример

См. в разделе [HTMLEdit пример](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

##  <a name="dhtmlediting_cmd_entry_func_type"></a>  DHTMLEDITING_CMD_ENTRY_FUNC_TYPE

Сопоставляет идентификатор команды редактирования командой, обработчик сообщений и элемент пользовательского интерфейса HTML.

```
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды (например, ID_EDIT_COPY).

*dhtmlcmdID*<br/>
HTML, команда, к которому изменения *cmdID* сопоставляет (например, IDM_COPY).

*member_func_name*<br/>
Имя функции обработчика сообщений, с которым сопоставляется команды.

*elemType*<br/>
Тип элемента пользовательского интерфейса; одно из AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX или AFX_UI_ELEMTYPE_RADIO.

### <a name="example"></a>Пример

См. в разделе [HTMLEdit пример](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
