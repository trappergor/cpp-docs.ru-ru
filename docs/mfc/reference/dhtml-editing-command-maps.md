---
title: "Схемы команд редактирования DHTML | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 89aa66d3a1e85183baaba21f001b60e080895f7f
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="dhtml-editing-command-maps"></a>Схемы команд редактирования DHTML
Следующие макросы можно использовать для сопоставления команд редактирования DHTML [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-производные классы. Пример их использования см. в разделе [HTMLEdit пример](../../visual-cpp-samples.md).  
  
### <a name="dhtml-editing-command-map-macros"></a>Макросы схемы команд редактирования DHTML  
  
|||  
|-|-|  
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|Объявляет карты команд редактирования DHTML в классе.|  
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|Начинается определение сопоставления команд редактирования DHTML в пределах класса.|  
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|Отмечает конец карты команд редактирования DHTML.|  
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|Сопоставляет идентификатор команды команду редактирования HTML.|  
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|Сопоставляет идентификатор команды команды редактирования HTML и обработчик сообщений.|  
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|Сопоставляет идентификатор команды команды редактирования HTML и элемент пользовательского интерфейса.|  
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|Сопоставляет идентификатор команды редактирования команды, обработчик сообщений и элемент пользовательского интерфейса HTML.|  
  
##  <a name="declare_dhtmlediting_cmdmap"></a>DECLARE_DHTMLEDITING_CMDMAP  
 Объявляет карты команд редактирования DHTML в классе.  
  
```  
DECLARE_DHTMLEDITING_CMDMAP(className)   
```  
  
### <a name="parameters"></a>Параметры  
 `className`  
 Имя класса.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос будет использоваться в определении [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-производные классы.  
  
 Используйте [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap) реализовать карты.  
  
### <a name="example"></a>Пример  
 В разделе [HTMLEdit пример](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxhtml.h  
  
##  <a name="begin_dhtmlediting_cmdmap"></a>BEGIN_DHTMLEDITING_CMDMAP  
 Начинается определение сопоставления команд редактирования DHTML в пределах класса.  
  
```  
BEGIN_DHTMLEDITING_CMDMAP(className)   
```  
  
### <a name="parameters"></a>Параметры  
 `className`  
 Имя класса, содержащего карту команд редактирования DHTML. Этот класс должен наследовать прямо или косвенно [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) и включить [DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap) макрос в соответствии с определением класса.  
  
### <a name="remarks"></a>Примечания  
 Добавьте карту команд редактирования DHTML в класс для сопоставления команд пользовательского интерфейса для команд редактирования HTML.  
  
 Место `BEGIN_DHTMLEDITING_CMDMAP` макрос в файл класса реализации (CPP), за которым следует [DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry) макросы для команд является сопоставление класса (например, из **ID_EDIT_CUT** для **IDM_CUT**). Используйте [END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap) макрос для обозначения конца карты событий.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxhtml.h  
  
##  <a name="end_dhtmlediting_cmdmap"></a>END_DHTMLEDITING_CMDMAP  
 Отмечает конец карты команд редактирования DHTML.  
  
```  
END_DHTMLEDITING_CMDMAP()   
```  
  
### <a name="remarks"></a>Примечания  
 Использовать в сочетании с [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap).  
  
### <a name="example"></a>Пример  
 В разделе [HTMLEdit пример](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry"></a>DHTMLEDITING_CMD_ENTRY  
 Сопоставляет идентификатор команды команду редактирования HTML.  
  
```  
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)   
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Идентификатор команды (такие как **ID_EDIT_COPY**).  
  
 `dhtmlcmdID`  
 HTML, редактирование команды, к которому `cmdID` сопоставляет (такие как **IDM_COPY**).  
  
### <a name="example"></a>Пример  
 В разделе [HTMLEdit пример](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_func"></a>DHTMLEDITING_CMD_ENTRY_FUNC  
 Сопоставляет идентификатор команды команды редактирования HTML и обработчик сообщений.  
  
```  
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)   
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Идентификатор команды (такие как **ID_EDIT_COPY**).  
  
 `dhtmlcmdID`  
 HTML, редактирование команды, к которому `cmdID` сопоставляет (такие как **IDM_COPY**).  
  
 `member_func_name`  
 Имя функции обработчика сообщений, с которым сопоставлен команды.  
  
### <a name="example"></a>Пример  
 В разделе [HTMLEdit пример](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_type"></a>DHTMLEDITING_CMD_ENTRY_TYPE  
 Сопоставляет идентификатор команды команды редактирования HTML и элемент пользовательского интерфейса.  
  
```  
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)  
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Идентификатор команды (такие как **ID_EDIT_COPY**).  
  
 `dhtmlcmdID`  
 HTML, редактирование команды, к которому `cmdID` сопоставляет (такие как **IDM_COPY**).  
  
 `elemType`  
 Тип элемента пользовательского интерфейса; один из **AFX_UI_ELEMTYPE_NORMAL**, **AFX_UI_ELEMTYPE_CHECKBOX**, или **AFX_UI_ELEMTYPE_RADIO**.  
  
### <a name="example"></a>Пример  
 В разделе [HTMLEdit пример](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_func_type"></a>DHTMLEDITING_CMD_ENTRY_FUNC_TYPE  
 Сопоставляет идентификатор команды редактирования команды, обработчик сообщений и элемент пользовательского интерфейса HTML.  
  
```  
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)   
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Идентификатор команды (такие как **ID_EDIT_COPY**).  
  
 `dhtmlcmdID`  
 HTML, редактирование команды, к которому `cmdID` сопоставляет (такие как **IDM_COPY**).  
  
 `member_func_name`  
 Имя функции обработчика сообщений, с которым сопоставлен команды.  
  
 `elemType`  
 Тип элемента пользовательского интерфейса; один из **AFX_UI_ELEMTYPE_NORMAL**, **AFX_UI_ELEMTYPE_CHECKBOX**, или **AFX_UI_ELEMTYPE_RADIO**.  
  
### <a name="example"></a>Пример  
 В разделе [HTMLEdit пример](../../visual-cpp-samples.md).  

### <a name="requirements"></a>Требования  
  **Заголовок** afxhtml.h  
    
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

