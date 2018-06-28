---
title: Класс COleCmdUI | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleCmdUI
- AFXDOCOBJ/COleCmdUI
- AFXDOCOBJ/COleCmdUI::COleCmdUI
- AFXDOCOBJ/COleCmdUI::Enable
- AFXDOCOBJ/COleCmdUI::SetCheck
- AFXDOCOBJ/COleCmdUI::SetText
dev_langs:
- C++
helpviewer_keywords:
- COleCmdUI [MFC], COleCmdUI
- COleCmdUI [MFC], Enable
- COleCmdUI [MFC], SetCheck
- COleCmdUI [MFC], SetText
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c80c3b81b804a66e70efe9269b12d4e18d31c676
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040718"
---
# <a name="colecmdui-class"></a>Класс COleCmdUI
Реализует метод для MFC, позволяющий обновлять состояние объектов ИП, связанных с зависимыми от `IOleCommandTarget`функциями вашего приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleCmdUI : public CCmdUI  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleCmdUI::COleCmdUI](#colecmdui)|Создает объект `COleCmdUI`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleCmdUI::Enable](#enable)|Устанавливает или снимает флаг команды enable.|  
|[COleCmdUI::SetCheck](#setcheck)|Задает состояние включения/выключения переключателя команды.|  
|[COleCmdUI::SetText](#settext)|Возвращает текстовую строку имени или состояния для команды.|  
  
## <a name="remarks"></a>Примечания  
 В приложении, которое не включена для DocObjects, когда пользователь просматривает меню в приложении MFC процессов **UPDATE_COMMAND_UI** notifcations. Каждое уведомление предоставляется [CCmdUI](../../mfc/reference/ccmdui-class.md) объект, который можно обрабатывать для отражения состояния определенной команды. Однако при включении приложения для DocObjects MFC обрабатывает **UPDATE_OLE_COMMAND_UI** уведомления и назначит `COleCmdUI` объектов.  
  
 `COleCmdUI` позволяет DocObject для получения команд, которые происходят в пользовательском интерфейсе контейнера (например, FileNew, Open, печати и т. д), а контейнер для получения команд, создаваемых в DocObject пользовательского интерфейса. Несмотря на то что `IDispatch` может использоваться для перенаправления те же команды `IOleCommandTarget` предоставляет простой способ запроса и выполнить, так как он использует стандартный набор команд, обычно без аргументов, и участвует никакой информации о типе. `COleCmdUI` можно использовать для включения, обновления и задать другие свойства команд DocObject пользовательского интерфейса. При необходимости для вызова команды вызвать [COleServerDoc::OnExecOleCmd](../../mfc/reference/coleserverdoc-class.md#onexecolecmd).  
  
 Дополнительные сведения о DocObjects см. в разделе [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) и [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md). См. также [первые шаги в Интернете: активные документы](../../mfc/active-documents-on-the-internet.md) и [активные документы](../../mfc/active-documents-on-the-internet.md).  
  
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
 *rgCmds*  
 Список поддерживаемых команд, связанных с указанным кодом GUID. **OLECMD** структуры связывают команд с помощью командной строки.  
  
 *cCmds*  
 Количество команд в *rgCmds*.  
  
 *pGroup*  
 Указатель на GUID, который определяет набор команд.  
  
### <a name="remarks"></a>Примечания  
 `COleCmdUI` Объект обеспечивает программный интерфейс для обновления объектов DocObject пользовательского интерфейса, таких как пункты меню или кнопок панели управления. Объекты пользовательского интерфейса может быть включена, отключена, проверяется или очистить через `COleCmdUI` объекта.  
  
##  <a name="enable"></a>  COleCmdUI::Enable  
 Вызывайте эту функцию, чтобы задать флаг команды `COleCmdUI` объект **OLECOMDF_ENABLED**, который указывает интерфейс, что команда была доступна и включена, или снимите флаг команды.  
  
```  
virtual void Enable(BOOL bOn);
```  
  
### <a name="parameters"></a>Параметры  
 *bВ системах*  
 Указывает ли команды, связанные с `COleCmdUI` включен или отключен объект. Ненулевое значение включает команды; 0 отключает команду.  
  
##  <a name="setcheck"></a>  COleCmdUI::SetCheck  
 Эта функция вызывается для задания состояния включения/выключения переключателя команды.  
  
```  
virtual void SetCheck(int nCheck);
```  
  
### <a name="parameters"></a>Параметры  
 *Проверьте*  
 Значение, определяющее, включить или выключить переключить ее состояние команды. Доступны следующие значения:  
  
|Значение|Описание:|  
|-----------|-----------------|  
|**1**|Задает команду, чтобы on.|  
|**2**|Задает команду, чтобы определено; не удается определить состояние, так как атрибут этой команды на и отключение состояния в подходящий вариант выбора.|  
|Любое другое значение|Задает команду, отключен.|  
  
##  <a name="settext"></a>  COleCmdUI::SetText  
 Эта функция используется для возврата строки имени или состоянии текст команды.  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszText*  
 Указатель на текст для использования с помощью команды.  
  
## <a name="see-also"></a>См. также  
 [CCmdUI-класс](../../mfc/reference/ccmdui-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



