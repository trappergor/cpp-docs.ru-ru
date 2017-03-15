---
title: "Класс CMouseManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMouseManager
dev_langs:
- C++
helpviewer_keywords:
- CMouseManager class
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
caps.latest.revision: 26
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 7ba50f976f6cf9d6b701e39304c50507cfa34cc5
ms.lasthandoff: 02/24/2017

---
# <a name="cmousemanager-class"></a>Класс CMouseManager
Позволяет пользователю связать различные команды с конкретным [CView](../../mfc/reference/cview-class.md) объекта, когда пользователь дважды щелкает внутри представления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMouseManager : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMouseManager::AddView](#addview)|Добавляет `CView` объект **настройки** диалоговое окно. **Настройки** диалоговое окно позволяет пользователю связать двойным щелчком с помощью команды, для каждого из перечисленных видов.|  
|[CMouseManager::GetViewDblClickCommand](#getviewdblclickcommand)|Возвращает команду, которая выполняется, когда пользователь дважды щелкает внутри указанного представления.|  
|[CMouseManager::GetViewIconId](#getviewiconid)|Возвращает значок, связанный с идентификатором указанного представления.|  
|[CMouseManager::GetViewIdByName](#getviewidbyname)|Возвращает идентификатор представления, связанные с именем указанного представления.|  
|[CMouseManager::GetViewNames](#getviewnames)|Получает список имен всех добавленных представления.|  
|[CMouseManager::LoadState](#loadstate)|Загружает `CMouseManager` состояния из реестра Windows.|  
|[CMouseManager::SaveState](#savestate)|Записывает `CMouseManager` состояние в реестр Windows.|  
|[CMouseManager::SetCommandForDblClk](#setcommandfordblclk)|Связывает предоставленной команды и предоставленный представления.|  
  
## <a name="remarks"></a>Примечания  
 `CMouseManager` Класс поддерживает коллекцию `CView` объектов. Каждое представление идентифицируется по имени и идентификатора. Эти представления отображаются в **настройки** диалоговое окно. Пользователь может изменить команду, которая связана с любого представления через **настройки** диалоговое окно. Соответствующая команда выполняется при двойном щелчке в этом представлении. Для этого с точки зрения программирования, необходимо обработать `WM_LBUTTONDBLCLK` сообщение и вызвать [CWinAppEx::OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick) в коде для этой функции `CView` объекта...  
  
 Не следует создавать `CMouseManager` объекта вручную. Создается платформой приложения. Оно также уничтожается автоматически, когда пользователь выходит из приложения. Чтобы получить указатель мыши manager для вашего приложения, вызовите [CWinAppEx::GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMouseManager`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmousemanager.h  
  
##  <a name="a-nameaddviewa--cmousemanageraddview"></a><a name="addview"></a>CMouseManager::AddView  
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
 Значок кода представления.  
  
 [in] `iId`  
 Идентификатор представления.  
  
 [in] `lpszViewName`  
 Имя представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Для поддержки пользовательских мыши поведение, представление должно быть зарегистрировано в `CMouseManager` объекта. Любой объект, производный от `CView` класс может быть зарегистрирован с помощью диспетчера мыши. Отображается строка и значок, связанный с представлением в **мыши** вкладке **Настройка** диалоговое окно.  
  
 За это отвечает программист должен создавать и поддерживать представления идентификаторов, таких как `iViewId` и `iId`.  
  
 Дополнительные сведения о том, как предоставить поведение мыши пользовательских см [Настройка мыши и клавиатуры](../../mfc/keyboard-and-mouse-customization.md).  
  
### <a name="example"></a>Пример  
 Ниже приведен пример, как получить указатель на `CMouseManager` объекта с помощью `CWinAppEx::GetMouseManager` метод и `AddView` метод в `CMouseManager` класса. Этот фрагмент кода является частью [пример коллекции состояния](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection&#4;](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]  
  
##  <a name="a-namegetviewdblclickcommanda--cmousemanagergetviewdblclickcommand"></a><a name="getviewdblclickcommand"></a>CMouseManager::GetViewDblClickCommand  
 Возвращает команду, которая выполняется, когда пользователь дважды щелкает внутри указанного представления.  
  
```  
UINT GetViewDblClickCommand(int iId) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iId`  
 Идентификатор представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор команды, если представление связано с помощью команды; в противном случае — 0.  
  
##  <a name="a-namegetviewiconida--cmousemanagergetviewiconid"></a><a name="getviewiconid"></a>CMouseManager::GetViewIconId  
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
 Этот метод завершится ошибкой, если представление сначала не зарегистрирован с помощью [CMouseManager::AddView](#addview).  
  
##  <a name="a-namegetviewidbynamea--cmousemanagergetviewidbyname"></a><a name="getviewidbyname"></a>CMouseManager::GetViewIdByName  
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
  
##  <a name="a-namegetviewnamesa--cmousemanagergetviewnames"></a><a name="getviewnames"></a>CMouseManager::GetViewNames  
 Получает список имен всех зарегистрированных представления.  
  
```  
void GetViewNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `listOfNames`  
 Ссылку на `CStringList` объект.  
  
### <a name="remarks"></a>Примечания  
 Этот метод заполняет параметр `listOfNames` с именами всех представлений, которые зарегистрированы с помощью [CMouseManager::AddView](#addview).  
  
##  <a name="a-nameloadstatea--cmousemanagerloadstate"></a><a name="loadstate"></a>CMouseManager::LoadState  
 Загружает состояние [CMouseManager класса](../../mfc/reference/cmousemanager-class.md) из реестра.  
  
```  
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Путь раздела реестра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Сведения о состоянии, загруженный из реестра содержит зарегистрированные представления идентификаторов представлений и связанные с ними команды. Если параметр `lpszProfileName` — `NULL`, эта функция загружает `CMouseManager` данные из реестра по умолчанию контролируется [CWinAppEx Class](../../mfc/reference/cwinappex-class.md).  
  
 В большинстве случаев не нужно непосредственно вызвать эту функцию. Он вызывается как часть процесса инициализации рабочей области. Дополнительные сведения о процессе инициализации рабочей области в разделе [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate).  
  
##  <a name="a-namesavestatea--cmousemanagersavestate"></a><a name="savestate"></a>CMouseManager::SaveState  
 Записывает состояние [CMouseManager класса](../../mfc/reference/cmousemanager-class.md) в реестре.  
  
```  
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Путь раздела реестра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Сведения о состоянии записываются в реестр включает все зарегистрированные представления, идентификаторов представлений и связанные с ними команды. Если параметр `lpszProfileName` — `NULL`, эта функция записывает `CMouseManager` данные для раздела реестра по умолчанию контролируется [CWinAppEx Class](../../mfc/reference/cwinappex-class.md).  
  
 В большинстве случаев не нужно непосредственно вызвать эту функцию. Он вызывается как часть процесса сериализации рабочей области. Дополнительные сведения о рабочей области процесса сериализации см. в разделе [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).  
  
##  <a name="a-namesetcommandfordblclka--cmousemanagersetcommandfordblclk"></a><a name="setcommandfordblclk"></a>CMouseManager::SetCommandForDblClk  
 Связывает команду с представлением, сначала зарегистрированной в диспетчере мыши.  
  
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
 Чтобы связать пользовательские команды с представлением, сначала необходимо зарегистрировать представление с помощью [CMouseManager::AddView](#addview). `AddView` Метод требует идентификатор представления как входной параметр. После регистрации представления можно вызвать `CMouseManager::SetCommandForDblClk` с же представление идентификатор входным параметром, который введен для `AddView`. После этого при двойном щелчке мыши в представлении зарегистрированных, приложение выполнит команду обозначается `uiCmd.` для поддержки поведения пользовательского мыши, также требуется настроить представление, зарегистрированных диспетчером мыши. Дополнительные сведения о поведении пользовательского мыши в разделе [Настройка мыши и клавиатуры]--brokenlink--(.. / мыши и клавиатура customization.md).  
  
 Если `uiCmd` имеет значение 0, указанное представление больше не будет связан с командой.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [Настройка мыши и клавиатуры](../../mfc/keyboard-and-mouse-customization.md)




