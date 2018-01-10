---
title: "Класс CContextMenuManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::AddMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuById
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuByName
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuNames
- AFXCONTEXTMENUMANAGER/CContextMenuManager::LoadState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ResetState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SaveState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SetDontCloseActiveMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ShowPopupMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::TrackPopupMenu
dev_langs: C++
helpviewer_keywords:
- CContextMenuManager [MFC], CContextMenuManager
- CContextMenuManager [MFC], AddMenu
- CContextMenuManager [MFC], GetMenuById
- CContextMenuManager [MFC], GetMenuByName
- CContextMenuManager [MFC], GetMenuNames
- CContextMenuManager [MFC], LoadState
- CContextMenuManager [MFC], ResetState
- CContextMenuManager [MFC], SaveState
- CContextMenuManager [MFC], SetDontCloseActiveMenu
- CContextMenuManager [MFC], ShowPopupMenu
- CContextMenuManager [MFC], TrackPopupMenu
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
caps.latest.revision: "32"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 38bfaec077501173fade6fa15fba3516cde534b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccontextmenumanager-class"></a>Класс CContextMenuManager
`CContextMenuManager` Управляет контекстные меню, также известные как контекстные меню.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CContextMenuManager : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CContextMenuManager::CContextMenuManager](#ccontextmenumanager)|Создает объект `CContextMenuManager`.|  
|`CContextMenuManager::~CContextMenuManager`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CContextMenuManager::AddMenu](#addmenu)|Добавляет новый контекстное меню.|  
|[CContextMenuManager::GetMenuById](#getmenubyid)|Возвращает дескриптор меню, связанное с идентификатором предоставленного ресурса.|  
|[CContextMenuManager::GetMenuByName](#getmenubyname)|Возвращает дескриптор для меню, которое соответствует имени указанного меню.|  
|[CContextMenuManager::GetMenuNames](#getmenunames)|Возвращает список имен меню.|  
|[CContextMenuManager::LoadState](#loadstate)|Загружает контекстные меню, хранящиеся в реестре Windows.|  
|[CContextMenuManager::ResetState](#resetstate)|Удаляет контекстные меню из меню диспетчера контекста.|  
|[CContextMenuManager::SaveState](#savestate)|Сохраняет контекстных меню в реестре Windows.|  
|[CContextMenuManager::SetDontCloseActiveMenu](#setdontcloseactivemenu)|Элементы управления ли `CContextMenuManager` закрывает active контекстное меню, при отображении новой контекстное меню.|  
|[CContextMenuManager::ShowPopupMenu](#showpopupmenu)|Отображает указанное контекстное меню.|  
|[CContextMenuManager::TrackPopupMenu](#trackpopupmenu)|Отображает указанное контекстное меню. Возвращает индекс команды меню.|  
  
## <a name="remarks"></a>Примечания  
 `CContextMenuManager`Управляет контекстными меню и гарантирует, что они имеют согласованного внешнего вида.  
  
 Не следует создавать `CContextMenuManager` объекта вручную. Платформа приложения создает `CContextMenuManager` объекта. Тем не менее, необходимо вызвать [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) при инициализации приложения. После инициализации диспетчера контекста, используйте метод [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager) для получения указателя на диспетчер контекста для вашего приложения.  
  
 Контекстные меню во время выполнения можно создать путем вызова `AddMenu`. Если вы хотите отобразить меню без первого получения ввода данных пользователем, вызовите `ShowPopupMenu`. `TrackPopupMenu`используется, если вы хотите создать меню и ожидает ввода пользователя. `TrackPopupMenu`Возвращает индекс выделенной команды или 0, если пользователь завершил работу без выбора элементов.  
  
 `CContextMenuManager` Также можно сохранять и загружать свое состояние в реестр Windows.  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как добавить меню `CContextMenuManager` , а также не удается закрыть активное всплывающее меню при `CContextMenuManager` объект отображает новое всплывающее меню. Этот фрагмент кода является частью [образец пользовательские страницы](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CContextMenuManager`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcontextmenumanager.h  
  
##  <a name="addmenu"></a>CContextMenuManager::AddMenu  
 Добавляет новый контекстное меню для [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).  
  
```  
BOOL AddMenu(
    UINT uiMenuNameResId,  
    UINT uiMenuResId);

 
BOOL AddMenu(
    LPCTSTR lpszName,  
    UINT uiMenuResId);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiMenuNameResId`  
 Идентификатор ресурса для строка, содержащая имя нового меню.  
  
 [in] `uiMenuResId`  
 Идентификатор ресурса меню  
  
 [in] `lpszName`  
 Строка, содержащая имя нового меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; 0, если происходит сбой метода.  
  
### <a name="remarks"></a>Примечания  
 Этот метод завершается ошибкой, если `uiMenuResId` недопустим или если другого меню с тем же именем уже присутствует в `CContextMenuManager`.  
  
##  <a name="ccontextmenumanager"></a>CContextMenuManager::CContextMenuManager  
 Создает [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) объекта.  
  
```  
CContextMenuManager();
```  
  
### <a name="remarks"></a>Примечания  
 В большинстве случаев не следует создавать `CContextMenuManager` вручную. Платформа приложения создает `CContextMenuManager` объекта. Необходимо вызвать [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) во время инициализации приложения. Чтобы получить указатель на диспетчер контекста, вызовите [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager).  
  
##  <a name="getmenubyid"></a>CContextMenuManager::GetMenuById  
 Возвращает дескриптор меню, связанное с идентификатором данного ресурса.  
  
```  
HMENU GetMenuById(UINT nMenuResId) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nMenuResId`  
 Идентификатор ресурса для меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор соответствующие пункты меню или `NULL` Если меню не найден.  
  
##  <a name="getmenubyname"></a>CContextMenuManager::GetMenuByName  
 Возвращает дескриптор для конкретного меню.  
  
```  
HMENU GetMenuByName(
    LPCTSTR lpszName,  
    UINT* puiOrigResID = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszName`  
 Строка, содержащая имя меню, для извлечения.  
  
 [выходной] `puiOrigResID`  
 Указатель на `UINT`. Этот параметр содержит идентификатор ресурса указанное меню, если найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор для меню, которое соответствует имени, указанное в параметре `lpszName`. `NULL`Если нет меню с именем `lpszName`.  
  
### <a name="remarks"></a>Примечания  
 Если этот метод находит меню, которое соответствует `lpszName`, `GetMenuByName` сохраняет идентификатор ресурса меню в параметре `puiOrigResID`.  
  
##  <a name="getmenunames"></a>CContextMenuManager::GetMenuNames  
 Возвращает список Добавить имена меню [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).  
  
```  
void GetMenuNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `listOfNames`  
 Ссылку на [CStringList](../../mfc/reference/cstringlist-class.md) параметра. Этот метод записывает список названий меню для данного параметра.  
  
##  <a name="loadstate"></a>CContextMenuManager::LoadState  
 Загружает данные, связанные с [CContextMenuManager класса](../../mfc/reference/ccontextmenumanager-class.md) из реестра Windows.  
  
```  
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Строка, содержащая относительный путь реестра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 `lpszProfileName` Параметр не абсолютный путь к записи реестра. Это относительный путь, который добавляется в конец раздел реестра по умолчанию для приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) и [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) соответственно.  
  
 Используйте метод [CContextMenuManager::SaveState](#savestate) сохранить контекстные меню в реестр.  
  
##  <a name="resetstate"></a>CContextMenuManager::ResetState  
 Удаляет все элементы из контекстного меню, связанных с [CContextMenuManager класса](../../mfc/reference/ccontextmenumanager-class.md).  
  
```  
virtual BOOL ResetState();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; `FALSE` при возникновении сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод очищает всплывающих меню и удаляет их из `CContextMenuManager`.  
  
##  <a name="savestate"></a>CContextMenuManager::SaveState  
 Сохраняет сведения, связанные с [CContextMenuManager класса](../../mfc/reference/ccontextmenumanager-class.md) в реестр Windows.  
  
```  
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Строка, содержащая относительный путь реестра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 `lpszProfileName` Параметр не абсолютный путь к записи реестра. Это относительный путь, который добавляется в конец раздел реестра по умолчанию для приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) и [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) соответственно.  
  
 Используйте метод [CContextMenuManager::LoadState](#loadstate) для загрузки с контекстными меню из реестра.  
  
##  <a name="setdontcloseactivemenu"></a>CContextMenuManager::SetDontCloseActiveMenu  
 Элементы управления ли [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) закрывает активное всплывающее меню, при отображении новой всплывающего меню.  
  
```  
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSet`  
 Логического параметра, который определяет, следует ли закрывать активное всплывающее меню. Значение `TRUE` указывает на активное всплывающее меню не закрыта. `FALSE`Указывает, что закрывается активное всплывающее меню.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `CContextMenuManager` закрывает активное всплывающее меню.  
  
##  <a name="showpopupmenu"></a>CContextMenuManager::ShowPopupMenu  
 Отображает указанное контекстное меню.  
  
```  
virtual BOOL ShowPopupMenu(
    UINT uiMenuResId,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bOwnMessage = FALSE,  
    BOOL bRightAlign = FALSE);

 
virtual CMFCPopupMenu* ShowPopupMenu(
    HMENU hmenuPopup,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bOwnMessage = FALSE,  
    BOOL bAutoDestroy = TRUE,  
    BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiMenuResId`  
 Идентификатор ресурса меню, которое будет отображаться этот метод.  
  
 [in] `x`  
 Горизонтальное смещение для контекстного меню в клиентских координатах.  
  
 [in] `y`  
 Вертикальное смещение для контекстного меню в клиентских координатах  
  
 [in] `pWndOwner`  
 Указатель на родительское окно элемента в контекстном меню.  
  
 [in] `bOwnMessage`  
 Логический параметр, указывающее способ маршрутизации сообщений. Если `bOwnMessage` — `FALSE`, используется стандартный маршрут MFC. В противном случае `pWndOwner` получает сообщения.  
  
 [in] `hmenuPopup`  
 Дескриптор меню, которое будет отображаться этот метод.  
  
 [in] `bAutoDestroy`  
 Логический параметр, указывает, будет ли автоматически уничтожается меню.  
  
 [in] `bRightAlign`  
 Логический параметр, который указывает способ выравнивания элементов меню. Если `bRightAlign` — `TRUE`, меню по правому краю порядок чтения справа налево.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первая перегрузка метода возвращает ненулевое значение, если метод успешно; показано меню в противном случае — 0. Вторая перегрузка метода возвращает указатель на [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) Если в контекстном меню отображаются правильно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод похож на метод [CContextMenuManager::TrackPopupMenu](#trackpopupmenu) в том, что оба метода отображения контекстного меню. Тем не менее `TrackPopupMenu` возвращает индекс команды меню.  
  
 Если параметр `bAutoDestroy` — `FALSE`, вручную необходимо вызвать наследуемого `DestroyMenu` метод для освобождения ресурсов памяти. Реализация по умолчанию `ShowPopupMenu` , не используйте параметр `bAutoDestroy`. Он предоставляется для использования в будущем или для пользовательских классов, производных от `CContextMenuManager` класса.  
  
##  <a name="trackpopupmenu"></a>CContextMenuManager::TrackPopupMenu  
 Отображает указанное контекстное меню и возвращает индекс команды выбранного контекстного меню.  
  
```  
virtual UINT TrackPopupMenu(
    HMENU hmenuPopup,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hmenuPopup`  
 Дескриптор, этот метод отображает контекстное меню.  
  
 [in] `x`  
 Горизонтальное смещение для контекстного меню в клиентских координатах.  
  
 [in] `y`  
 Вертикальная смещение для контекстного меню в клиентских координатах.  
  
 [in] `pWndOwner`  
 Указатель на родительское окно элемента в контекстном меню.  
  
 [in] `bRightAlign`  
 Логический параметр, который указывает способ выравнивания элементов меню. Если `bRightAlign` — `TRUE`, меню по правому краю порядок чтения справа налево. Если `bRightAlign` — `FALSE`, меню по левому краю порядок чтения справа налево.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор команды меню команды, выбранные пользователем; 0, если пользователь закрывает контекстное меню без выбора команды меню.  
  
### <a name="remarks"></a>Примечания  
 Этот метод работает как модальное вызов отображения контекстного меню. Приложение не будет продолжать следующая строка кода, пока пользователь закрывает контекстное меню или выбирает команду. Альтернативный метод, который можно использовать для отображения контекстного меню — [CContextMenuManager::ShowPopupMenu](#showpopupmenu). Этот метод не является модальным вызовом и не возвращает идентификатор выбранной команды.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)
