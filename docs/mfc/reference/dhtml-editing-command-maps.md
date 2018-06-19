---
title: Схемы команд редактирования DHTML | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69630d00b09534d97d5e46a8400b73f0e9d85b24
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375139"
---
# <a name="dhtml-editing-command-maps"></a>Схемы команд редактирования DHTML
Следующие макросы можно использовать для сопоставления команд редактирования DHTML [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-производные классы. Пример их использования см. в разделе [HTMLEdit пример](../../visual-cpp-samples.md).  
  
### <a name="dhtml-editing-command-map-macros"></a>Макросы схемы команд редактирования DHTML  
  
|||  
|-|-|  
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|Объявляет карты команд редактирования DHTML в классе.|  
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|Запускает определения карты команд редактирования DHTML в пределах класса.|  
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|Отмечает конец карты команд редактирования DHTML.|  
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|Сопоставляет идентификатор команды для команды редактирования HTML.|  
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|Сопоставляет идентификатор команды команды редактирования HTML и обработчик сообщений.|  
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|Сопоставляет идентификатор команды команды редактирования HTML и элемент пользовательского интерфейса.|  
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|Сопоставляет идентификатор команды для редактирования команд, обработчик сообщений и элемент пользовательского интерфейса HTML.|  
  
##  <a name="declare_dhtmlediting_cmdmap"></a>  DECLARE_DHTMLEDITING_CMDMAP  
 Объявляет карты команд редактирования DHTML в классе.  
  
```  
DECLARE_DHTMLEDITING_CMDMAP(className)   
```  
  
### <a name="parameters"></a>Параметры  
 `className`  
 Имя класса.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос будет использоваться в определении [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-производные классы.  
  
 Используйте [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap) реализовать схему.  
  
### <a name="example"></a>Пример  
 В разделе [HTMLEdit пример](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxhtml.h  
  
##  <a name="begin_dhtmlediting_cmdmap"></a>  BEGIN_DHTMLEDITING_CMDMAP  
 Запускает определения карты команд редактирования DHTML в пределах класса.  
  
```  
BEGIN_DHTMLEDITING_CMDMAP(className)   
```  
  
### <a name="parameters"></a>Параметры  
 `className`  
 Имя класса, содержащего карты команд редактирования DHTML. Этот класс должен наследоваться от прямо или косвенно [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) и включать [DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap) макрос в соответствии с определением класса.  
  
### <a name="remarks"></a>Примечания  
 Добавьте карту команд редактирования DHTML в класс для сопоставления команд пользовательского интерфейса команд редактирования HTML.  
  
 Место `BEGIN_DHTMLEDITING_CMDMAP` макрос в файле реализации (CPP) класса, за которым следует [DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry) макросы для команд, является сопоставление класса (например, из **ID_EDIT_CUT** для  **IDM_CUT**). Используйте [END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap) макрос для обозначения конца схема событий.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxhtml.h  
  
##  <a name="end_dhtmlediting_cmdmap"></a>  END_DHTMLEDITING_CMDMAP  
 Отмечает конец карты команд редактирования DHTML.  
  
```  
END_DHTMLEDITING_CMDMAP()   
```  
  
### <a name="remarks"></a>Примечания  
 Используется в сочетании с [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap).  
  
### <a name="example"></a>Пример  
 В разделе [HTMLEdit пример](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry"></a>  DHTMLEDITING_CMD_ENTRY  
 Сопоставляет идентификатор команды для команды редактирования HTML.  
  
```  
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)   
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Идентификатор команды (такие как **ID_EDIT_COPY**).  
  
 `dhtmlcmdID`  
 Команда, к которому изменения HTML `cmdID` сопоставляет (такие как **IDM_COPY**).  
  
### <a name="example"></a>Пример  
 В разделе [HTMLEdit пример](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_func"></a>  DHTMLEDITING_CMD_ENTRY_FUNC  
 Сопоставляет идентификатор команды команды редактирования HTML и обработчик сообщений.  
  
```  
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)   
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Идентификатор команды (такие как **ID_EDIT_COPY**).  
  
 `dhtmlcmdID`  
 Команда, к которому изменения HTML `cmdID` сопоставляет (такие как **IDM_COPY**).  
  
 `member_func_name`  
 Имя функции обработчик сообщений, с которым сопоставлен команды.  
  
### <a name="example"></a>Пример  
 В разделе [HTMLEdit пример](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_type"></a>  DHTMLEDITING_CMD_ENTRY_TYPE  
 Сопоставляет идентификатор команды команды редактирования HTML и элемент пользовательского интерфейса.  
  
```  
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)  
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Идентификатор команды (такие как **ID_EDIT_COPY**).  
  
 `dhtmlcmdID`  
 Команда, к которому изменения HTML `cmdID` сопоставляет (такие как **IDM_COPY**).  
  
 `elemType`  
 Тип элемента пользовательского интерфейса; один из **AFX_UI_ELEMTYPE_NORMAL**, **AFX_UI_ELEMTYPE_CHECKBOX**, или **AFX_UI_ELEMTYPE_RADIO**.  
  
### <a name="example"></a>Пример  
 В разделе [HTMLEdit пример](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_func_type"></a>  DHTMLEDITING_CMD_ENTRY_FUNC_TYPE  
 Сопоставляет идентификатор команды для редактирования команд, обработчик сообщений и элемент пользовательского интерфейса HTML.  
  
```  
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)   
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Идентификатор команды (такие как **ID_EDIT_COPY**).  
  
 `dhtmlcmdID`  
 Команда, к которому изменения HTML `cmdID` сопоставляет (такие как **IDM_COPY**).  
  
 `member_func_name`  
 Имя функции обработчик сообщений, с которым сопоставлен команды.  
  
 `elemType`  
 Тип элемента пользовательского интерфейса; один из **AFX_UI_ELEMTYPE_NORMAL**, **AFX_UI_ELEMTYPE_CHECKBOX**, или **AFX_UI_ELEMTYPE_RADIO**.  
  
### <a name="example"></a>Пример  
 В разделе [HTMLEdit пример](../../visual-cpp-samples.md).  

### <a name="requirements"></a>Требования  
  **Заголовок** afxhtml.h  
    
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
