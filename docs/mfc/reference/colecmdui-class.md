---
title: "Класс COleCmdUI | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleCmdUI
dev_langs:
- C++
helpviewer_keywords:
- document object server
- COleCmdUI class
- servers [C++], ActiveX documents
- docobject server
- servers [C++], doc objects
- ActiveX documents [C++], document server
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
caps.latest.revision: 21
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 38e7019d7636166262028d955455cee675824f8b
ms.lasthandoff: 02/24/2017

---
# <a name="colecmdui-class"></a>Класс COleCmdUI
Реализует метод для MFC, позволяющий обновлять состояние объектов ИП, связанных с зависимыми от `IOleCommandTarget`функциями вашего приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleCmdUI : public CCmdUI  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleCmdUI::COleCmdUI](#colecmdui)|Создает объект `COleCmdUI`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleCmdUI::Enable](#enable)|Устанавливает или снимает флаг enable команды.|  
|[COleCmdUI::SetCheck](#setcheck)|Задает состояние включения/выключения переключателя командной.|  
|[COleCmdUI::SetText](#settext)|Возвращает текстовую строку имени или состояние команды.|  
  
## <a name="remarks"></a>Примечания  
 В приложении, которое не включена для DocObjects, когда пользователь просматривает меню в приложении MFC процессов **UPDATE_COMMAND_UI** уведомления. Учитывая каждого уведомления [CCmdUI](../../mfc/reference/ccmdui-class.md) объект, который может обрабатываться в соответствии с состоянием определенной команды. Однако при включении приложения для DocObjects MFC обрабатывает **UPDATE_OLE_COMMAND_UI** уведомления и присваивает `COleCmdUI` объектов.  
  
 `COleCmdUI`позволяет DocObject получать команд, которые создаются в интерфейсе пользователя его контейнера (например, Файлсоздать, открытия, печати и т. д), а контейнер для получения команд, которые создаются в пользовательском интерфейсе DocObject. Хотя `IDispatch` может использоваться для отправки те же команды `IOleCommandTarget` обеспечивает простой способ для запроса и выполнить, так как он использует стандартный набор команд, обычно без аргументов, и никакой информации о типе участвует. `COleCmdUI`можно использовать для включения, обновления и задать другие свойства DocObject команд пользовательского интерфейса. Для вызова команды следует вызвать [COleServerDoc::OnExecOleCmd](../../mfc/reference/coleserverdoc-class.md#onexecolecmd).  
  
 Дополнительные сведения о DocObjects в разделе [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) и [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md). См. также [Интернет первые шаги: активные документы](../../mfc/active-documents-on-the-internet.md) и [активные документы](../../mfc/active-documents-on-the-internet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CCmdUI](../../mfc/reference/ccmdui-class.md)  
  
 `COleCmdUI`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdocobj.h  
  
##  <a name="a-namecolecmduia--colecmduicolecmdui"></a><a name="colecmdui"></a>COleCmdUI::COleCmdUI  
 Создает `COleCmdUI` объекта, связанного с командой конкретного пользовательского интерфейса.  
  
```  
COleCmdUI(
    OLECMD* rgCmds,  
    ULONG cCmds,  
    const GUID* m_pGroup);
```  
  
### <a name="parameters"></a>Параметры  
 `rgCmds`  
 Список поддерживаемых команд, связанных с указанным кодом GUID. **OLECMD** структуры связывают команд с помощью командной строки.  
  
 *cCmds*  
 Число команд в `rgCmds`.  
  
 `pGroup`  
 Указатель на GUID, который определяет набор команд.  
  
### <a name="remarks"></a>Примечания  
 `COleCmdUI` Объект предоставляет программный интерфейс для обновления DocObject объекты пользовательского интерфейса, такие как элементы меню или кнопок панели управления. Объекты пользовательского интерфейса можно быть включена, отключена, установлен или снят через `COleCmdUI` объекта.  
  
##  <a name="a-nameenablea--colecmduienable"></a><a name="enable"></a>COleCmdUI::Enable  
 Вызвать эту функцию, чтобы задать флаг команды `COleCmdUI` объект **OLECOMDF_ENABLED**, который указывает интерфейс, что команда доступна и включена, или снимите флаг команды.  
  
```  
virtual void Enable(BOOL bOn);
```  
  
### <a name="parameters"></a>Параметры  
 `bOn`  
 Указывает, связан ли команда `COleCmdUI` включен или отключен объект. Ненулевое значение включает команду; 0 отключает команду.  
  
##  <a name="a-namesetchecka--colecmduisetcheck"></a><a name="setcheck"></a>COleCmdUI::SetCheck  
 Эта функция вызывается для задания состояния включения/выключения переключателя командной.  
  
```  
virtual void SetCheck(int nCheck);
```  
  
### <a name="parameters"></a>Параметры  
 `nCheck`  
 Значение, определяющее состояние включения/выключения переключателя командной. Доступны следующие значения:  
  
|Значение|Описание|  
|-----------|-----------------|  
|**1**|Задает команду, чтобы на.|  
|**2**|Задает команду, чтобы определено; не удается определить состояние, так как атрибут этой команды на и отключение состояний в подходящий вариант выбора.|  
|любое другое значение|Задает команду, отключен.|  
  
##  <a name="a-namesettexta--colecmduisettext"></a><a name="settext"></a>COleCmdUI::SetText  
 Эта функция вызывается для возврата строки имени или состоянии текст для команды.  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszText`  
 Указатель на текст, используемые с командой.  
  
## <a name="see-also"></a>См. также  
 [CCmdUI-класс](../../mfc/reference/ccmdui-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




