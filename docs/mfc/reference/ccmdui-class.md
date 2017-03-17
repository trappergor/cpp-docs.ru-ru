---
title: "Класс CCmdUI | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCmdUI
- AFXWIN/CCmdUI
- AFXWIN/CCmdUI::ContinueRouting
- AFXWIN/CCmdUI::Enable
- AFXWIN/CCmdUI::SetCheck
- AFXWIN/CCmdUI::SetRadio
- AFXWIN/CCmdUI::SetText
- AFXWIN/CCmdUI::m_nID
- AFXWIN/CCmdUI::m_nIndex
- AFXWIN/CCmdUI::m_pMenu
- AFXWIN/CCmdUI::m_pOther
- AFXWIN/CCmdUI::m_pSubMenu
dev_langs:
- C++
helpviewer_keywords:
- user interfaces, updating
- states, updating user interface object
- updating user interfaces for commands
- commands [C++], updating UI
- CCmdUI class
- toolbars [C++], updating
- command user interface
- menus [C++], updating as context changes
- buttons [C++], updating as context changes
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
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
ms.openlocfilehash: beb84a0f0f96c7a8acb5c432c7402b3e62b94518
ms.lasthandoff: 02/24/2017

---
# <a name="ccmdui-class"></a>CCmdUI-класс
Используется только в `ON_UPDATE_COMMAND_UI` обработчик в `CCmdTarget`-производного класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CCmdUI  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCmdUI::ContinueRouting](#continuerouting)|Указывает механизму маршрутизации команд для продолжения рассылки текущее сообщение по цепочке обработчиков.|  
|[CCmdUI::Enable](#enable)|Включение или отключение элементов пользовательского интерфейса для этой команды.|  
|[CCmdUI::SetCheck](#setcheck)|Задает состояние проверки элемента пользовательского интерфейса для этой команды.|  
|[CCmdUI::SetRadio](#setradio)|Как `SetCheck` функция-член, но работает с групп переключателей.|  
|[CCmdUI::SetText](#settext)|Задает текст для элемента пользовательского интерфейса для этой команды.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCmdUI::m_nID](#m_nid)|Идентификатор объекта пользовательского интерфейса.|  
|[CCmdUI::m_nIndex](#m_nindex)|Индекс объекта пользовательского интерфейса.|  
|[CCmdUI::m_pMenu](#m_pmenu)|Указывает меню, представленного `CCmdUI` объекта.|  
|[CCmdUI::m_pOther](#m_pother)|Указывает на объект окна, которому было отправлено уведомление.|  
|[CCmdUI::m_pSubMenu](#m_psubmenu)|Указывает автономной подменю представленного `CCmdUI` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CCmdUI`не имеет базового класса.  
  
 Когда пользователь приложения извлекает меню, каждый меню элемента необходимо знать, является ли он должен отображаться как включенные или отключена. Цель команды меню предоставляет эти сведения при реализации `ON_UPDATE_COMMAND_UI` обработчика. Для каждого из объектов пользовательского интерфейса команд в приложении используйте окно свойств для создания прототипа запись и функция схемы сообщений для каждого обработчика.  
  
 Когда меню загружена, платформа ищет и вызывает каждый `ON_UPDATE_COMMAND_UI` обработчик, вызывает каждый обработчик `CCmdUI` член функции, такие как **включить** и **проверка**, и платформа соответствующим образом отображает каждый элемент меню.  
  
 Элемент меню можно заменить кнопки панели элементов управления или другой объект пользовательского интерфейса команды без изменения кода в `ON_UPDATE_COMMAND_UI` обработчика.  
  
 В следующей таблице перечислены эффект `CCmdUI`функции-члены имеют на различные элементы пользовательского интерфейса команды.  
  
|Элемент пользовательского интерфейса|Включить|SetCheck|SetRadio|SetText|  
|--------------------------|------------|--------------|--------------|-------------|  
|Элемент меню|Включает или отключает|(×) И снятии флажка|Проверки, используя точка (•)|Наборы элементов текста|  
|Кнопки панели инструментов|Включает или отключает|Выбирает, приводит к отмене выбора, или неопределенное состояние|Совпадает с`SetCheck`|(Неприменимо)|  
|Панели строки состояния|Текст становится видимым или невидимым|Задает границы исчезающего или обычный|Совпадает с`SetCheck`|Задает текст панели|  
|Обычная кнопка в`CDialogBar`|Включает или отключает|Проверяет или снимает флажок|Совпадает с`SetCheck`|Задает кнопку текста|  
|Обычный элемент управления в`CDialogBar`|Включает или отключает|(Неприменимо)|(Неприменимо)|Задает текст окна|  
  
 Дополнительные сведения об использовании этого класса см. [как обновление объектов пользовательского интерфейса](../../mfc/how-to-update-user-interface-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CCmdUI`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="continuerouting"></a>CCmdUI::ContinueRouting  
 Вызовите эту функцию-член определить механизм маршрутизации команд для продолжения рассылки текущее сообщение по цепочке обработчиков.  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>Примечания  
 Это функция дополнительный член, который должен использоваться в сочетании с `ON_COMMAND_EX` обработчик, который возвращает **FALSE**. Дополнительные сведения см. в разделе [технические примечание 6](../../mfc/tn006-message-maps.md).  
  
##  <a name="enable"></a>CCmdUI::Enable  
 Вызовите эту функцию-член для включения или отключения элементов пользовательского интерфейса для этой команды.  
  
```  
virtual void Enable(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bOn`  
 **Значение TRUE,** для включения элемента, **FALSE** его отключить.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#46;](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#47;](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]  
  
##  <a name="m_nid"></a>CCmdUI::m_nID  
 Идентификатор элемента меню, кнопки панели инструментов или другого объекта пользовательского интерфейса, представленного `CCmdUI` объекта.  
  
```  
UINT m_nID;  
```  
  
##  <a name="m_nindex"></a>CCmdUI::m_nIndex  
 Индекс элемента меню, кнопки панели инструментов или другого объекта пользовательского интерфейса, представленного `CCmdUI` объекта.  
  
```  
UINT m_nIndex;  
```  
  
##  <a name="m_pmenu"></a>CCmdUI::m_pMenu  
 Указатель (из `CMenu` типа) в меню, представленного `CCmdUI` объекта.  
  
```  
CMenu* m_pMenu;  
```  
  
### <a name="remarks"></a>Примечания  
 **NULL** Если элемент не меню.  
  
##  <a name="m_psubmenu"></a>CCmdUI::m_pSubMenu  
 Указатель (из `CMenu` типа) для автономной подменю представленного `CCmdUI` объекта.  
  
```  
CMenu* m_pSubMenu;  
```  
  
### <a name="remarks"></a>Примечания  
 **NULL** Если элемент не меню. Если меню «sub» — это всплывающее окно `m_nID` содержит идентификатор первого элемента в контекстном меню. Дополнительные сведения см. в разделе [Технические заметки 21](../../mfc/tn021-command-and-message-routing.md).  
  
##  <a name="m_pother"></a>CCmdUI::m_pOther  
 Указатель (типа `CWnd`) на объект окна, например панель инструментов или состояния, который отправил уведомление.  
  
```  
CWnd* m_pOther;  
```  
  
### <a name="remarks"></a>Примечания  
 **NULL** , является ли элемент меню или значение, отличное от `CWnd` объекта.  
  
##  <a name="setcheck"></a>CCmdUI::SetCheck  
 Вызовите эту функцию-член присвоено состояние флажка соответствующий элемент пользовательского интерфейса для этой команды.  
  
```  
virtual void SetCheck(int nCheck = 1);
```  
  
### <a name="parameters"></a>Параметры  
 `nCheck`  
 Указывает состояние проверки для задания. Если 0, снимает; Если 1, проверка; и если 2, задает неопределенным.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член работает для элементов меню и кнопки панели инструментов. Неопределенное состояние применяется только к кнопкам панели инструментов.  
  
##  <a name="setradio"></a>CCmdUI::SetRadio  
 Вызовите эту функцию-член присвоено состояние флажка соответствующий элемент пользовательского интерфейса для этой команды.  
  
```  
virtual void SetRadio(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bOn`  
 **Значение TRUE,** для включения элемента; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член работает как `SetCheck`, за исключением того, что он работает на элементы пользовательского интерфейса, действующий как часть группы переключателей. Сняв флажок других элементов в группе не выполняется автоматически, если не сами элементы однородной работы группы переключателей.  
  
##  <a name="settext"></a>CCmdUI::SetText  
 Вызовите эту функцию-член для задания текста элемента пользовательского интерфейса для этой команды.  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszText`  
 Указатель на строку текста.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#48;](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MDI](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)

