---
title: "Класс CMouseManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMouseManager
- AFXMOUSEMANAGER/CMouseManager
- AFXMOUSEMANAGER/CMouseManager::AddView
- AFXMOUSEMANAGER/CMouseManager::GetViewDblClickCommand
- AFXMOUSEMANAGER/CMouseManager::GetViewIconId
- AFXMOUSEMANAGER/CMouseManager::GetViewIdByName
- AFXMOUSEMANAGER/CMouseManager::GetViewNames
- AFXMOUSEMANAGER/CMouseManager::LoadState
- AFXMOUSEMANAGER/CMouseManager::SaveState
- AFXMOUSEMANAGER/CMouseManager::SetCommandForDblClk
dev_langs:
- C++
helpviewer_keywords:
- CMouseManager [MFC], AddView
- CMouseManager [MFC], GetViewDblClickCommand
- CMouseManager [MFC], GetViewIconId
- CMouseManager [MFC], GetViewIdByName
- CMouseManager [MFC], GetViewNames
- CMouseManager [MFC], LoadState
- CMouseManager [MFC], SaveState
- CMouseManager [MFC], SetCommandForDblClk
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7d019bedd63e7b7700ec91309c9ccaa0a41bf1ed
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2018
---
# <a name="cmousemanager-class"></a>Класс CMouseManager
Позволяет пользователю связать различные команды с указанным [CView](../../mfc/reference/cview-class.md) объекта, когда пользователь дважды щелкает внутри представления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMouseManager : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMouseManager::AddView](#addview)|Добавляет `CView` объект **настройки** диалоговое окно. **Настройки** диалоговое окно позволяет пользователю связать двойным щелчком с помощью команды для каждого из перечисленных представлений.|  
|[CMouseManager::GetViewDblClickCommand](#getviewdblclickcommand)|Возвращает команду, которая выполняется, когда пользователь дважды щелкает внутри указанного представления.|  
|[CMouseManager::GetViewIconId](#getviewiconid)|Возвращает значок, связанный с идентификатором указанного представления.|  
|[CMouseManager::GetViewIdByName](#getviewidbyname)|Возвращает идентификатор представления, связанные с именем указанного представления.|  
|[CMouseManager::GetViewNames](#getviewnames)|Возвращает список всех имен добавлено представление.|  
|[CMouseManager::LoadState](#loadstate)|Загружает `CMouseManager` состояния из реестра Windows.|  
|[CMouseManager::SaveState](#savestate)|Записывает `CMouseManager` состояния в реестр Windows.|  
|[CMouseManager::SetCommandForDblClk](#setcommandfordblclk)|Связывает предоставленной команды и указанного представления.|  
  
## <a name="remarks"></a>Примечания  
 `CMouseManager` Класс поддерживает коллекцию `CView` объектов. Каждое представление определяется по имени и идентификатора. Эти представления отображаются в **настройки** диалоговое окно. Пользователь может изменить команду, которая связана с любого представления через **настройки** диалоговое окно. Связанная команда выполняется при двойном щелчке в этом представлении. Для этого с точки зрения программирования, необходимо обработать `WM_LBUTTONDBLCLK` сообщение и вызывают функцию [CWinAppEx::OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick) функции в коде, `CView` объекта...  
  
 Не следует создавать `CMouseManager` объекта вручную. Создается платформой приложения. Он будет также быть удален автоматически, когда пользователь выходит из приложения. Чтобы получить указатель мыши manager для вашего приложения, вызовите [CWinAppEx::GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMouseManager`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmousemanager.h  
  
##  <a name="addview"></a>  CMouseManager::AddView  
 Регистрирует [CView](../../mfc/reference/cview-class.md) объекта с [CMouseManager класса](../../mfc/reference/cmousemanager-class.md) для поддержки поведения пользовательского мыши.  
  
```  
BOOL AddView(
    int iViewId,  
    UINT uiViewNameResId,  
    UINT uiIconId = 0);

 
BOOL AddView(
    int iId,  
    LPCTSTR lpszViewName,  
    UINT uiIconId = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iViewId`  
 Идентификатор представления.  
  
 [in] `uiViewNameResId`  
 Идентификатор строки ресурса, который ссылается на имя представления.  
  
 [in] `uiIconId`  
 Идентификатор представления значка.  
  
 [in] `iId`  
 Идентификатор представления.  
  
 [in] `lpszViewName`  
 Имя представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Для поддержки возможности пользовательских мыши представления должны быть зарегистрированы в `CMouseManager` объекта. Любой объект, производный от `CView` класса могут быть зарегистрированы с помощью диспетчера мыши. Строка и значок, связанный с представлением, отображаются в **мыши** вкладке **Настройка** диалоговое окно.  
  
 Возлагается на программиста для создания и настройки представления идентификаторов, такие как `iViewId` и `iId`.  
  
 Дополнительные сведения о том, как предоставить поведение пользовательской мыши см. в разделе [Настройка мыши и клавиатуры](../../mfc/keyboard-and-mouse-customization.md).  
  
### <a name="example"></a>Пример  
 В следующем примере показано, как получить указатель на `CMouseManager` объектов с помощью `CWinAppEx::GetMouseManager` метод и `AddView` метод в `CMouseManager` класса. Этот фрагмент кода является частью [образец сбор данных о состоянии](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection#4](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]  
  
##  <a name="getviewdblclickcommand"></a>  CMouseManager::GetViewDblClickCommand  
 Возвращает команду, которая выполняется, когда пользователь дважды щелкает внутри указанного представления.  
  
```  
UINT GetViewDblClickCommand(int iId) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iId`  
 Идентификатор представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор команды, если представление, которое связано с помощью команды; в противном случае — 0.  
  
##  <a name="getviewiconid"></a>  CMouseManager::GetViewIconId  
 Получает значок, связанный с идентификатором представления.  
  
```  
UINT GetViewIconId(int iViewId) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iViewId`  
 Идентификатор представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор ресурса значка в случае успешного выполнения; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод завершится с ошибкой, если представление сначала не зарегистрирован с помощью [CMouseManager::AddView](#addview).  
  
##  <a name="getviewidbyname"></a>  CMouseManager::GetViewIdByName  
 Извлекает идентификатор представления, связанные с именем представления.  
  
```  
int GetViewIdByName(LPCTSTR lpszName) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszName`  
 Имя представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор представления, в случае успешного выполнения; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод выполняет поиск через представления, зарегистрированные с помощью [CMouseManager::AddView](#addview).  
  
##  <a name="getviewnames"></a>  CMouseManager::GetViewNames  
 Получает список имен всех зарегистрированных представления.  
  
```  
void GetViewNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `listOfNames`  
 Ссылку на `CStringList` объекта.  
  
### <a name="remarks"></a>Примечания  
 Этот метод заполняет параметр `listOfNames` с именами всех представлений, которые зарегистрированы с помощью [CMouseManager::AddView](#addview).  
  
##  <a name="loadstate"></a>  CMouseManager::LoadState  
 Загружает состояние [CMouseManager класса](../../mfc/reference/cmousemanager-class.md) из реестра.  
  
```  
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Путь реестра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Содержит сведения о состоянии, загруженный из реестра, зарегистрированные представления идентификаторов представлений и связанные команды. Если параметр `lpszProfileName` — `NULL`, эта функция загружает `CMouseManager` данные из реестра по умолчанию управляется [CWinAppEx класс](../../mfc/reference/cwinappex-class.md).  
  
 В большинстве случаев не нужно непосредственно вызвать эту функцию. Он вызывается как часть процесса инициализации рабочей области. Дополнительные сведения о процессе инициализации рабочей области в разделе [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate).  
  
##  <a name="savestate"></a>  CMouseManager::SaveState  
 Записывает состояние [CMouseManager класса](../../mfc/reference/cmousemanager-class.md) в реестре.  
  
```  
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Путь реестра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Содержит сведения о состоянии, записываются в реестр, все зарегистрированные представления, просмотр идентификаторов и связанные команды. Если параметр `lpszProfileName` — `NULL`, эта функция записывает `CMouseManager` данных в расположение реестра по умолчанию, которые управляются [CWinAppEx класс](../../mfc/reference/cwinappex-class.md).  
  
 В большинстве случаев не нужно непосредственно вызвать эту функцию. Он вызывается как часть процесса сериализации рабочей области. Дополнительные сведения о рабочей области процесса сериализации см. в разделе [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).  
  
##  <a name="setcommandfordblclk"></a>  CMouseManager::SetCommandForDblClk  
 Связывает пользовательской команды с представлением, сначала зарегистрированных диспетчером мыши.  
  
```  
void SetCommandForDblClk(
    int iViewId,  
    UINT uiCmd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iViewId`  
 Идентификатор представления.  
  
 [in] `uiCmd`  
 Идентификатор команды.  
  
### <a name="remarks"></a>Примечания  
 Чтобы связать пользовательской команды с представлением, необходимо сначала зарегистрировать представления с помощью [CMouseManager::AddView](#addview). `AddView` Методу требуется идентификатор представления в качестве входного параметра. После регистрации представления можно вызвать `CMouseManager::SetCommandForDblClk` с того же представления идентификатора входным параметром, предоставленный для `AddView`. После этого при двойном щелчке мыши в представлении зарегистрированных, приложение выполнит команду обозначается `uiCmd.` для поддержки поведения пользовательского мыши, также необходимо будет настроить представление, зарегистрированных диспетчером мыши. Дополнительные сведения о поведении пользовательского мыши см. в разделе [Настройка мыши и клавиатуры](../keyboard-and-mouse-customization.md).  
  
 Если `uiCmd` имеет значение 0, указанное представление больше не будет связан с командой.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)   
 [Настройка мыши и клавиатуры](../../mfc/keyboard-and-mouse-customization.md)



