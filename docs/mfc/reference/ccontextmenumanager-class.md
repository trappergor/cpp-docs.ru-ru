---
title: "Класс CContextMenuManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- CContextMenuManager class
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
caps.latest.revision: 32
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: fab322d0c60b33454504620170d9c77a98401ec8
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="ccontextmenumanager-class"></a>Класс CContextMenuManager
`CContextMenuManager` Объекта управляет контекстными меню, также известный как контекстные меню.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CContextMenuManager : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CContextMenuManager::CContextMenuManager](#ccontextmenumanager)|Создает объект `CContextMenuManager`.|  
|`CContextMenuManager::~CContextMenuManager`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CContextMenuManager::AddMenu](#addmenu)|Добавляет новый контекстное меню.|  
|[CContextMenuManager::GetMenuById](#getmenubyid)|Возвращает дескриптор меню, связанного с идентификатором предоставленного ресурса.|  
|[CContextMenuManager::GetMenuByName](#getmenubyname)|Возвращает дескриптор меню, которое соответствует имени предоставленного меню.|  
|[CContextMenuManager::GetMenuNames](#getmenunames)|Возвращает список названий меню.|  
|[CContextMenuManager::LoadState](#loadstate)|Загружает контекстных меню, хранящиеся в реестре Windows.|  
|[CContextMenuManager::ResetState](#resetstate)|Удаляет контекстные меню из меню диспетчера контекста.|  
|[CContextMenuManager::SaveState](#savestate)|Сохраняет контекстные меню в реестре Windows.|  
|[CContextMenuManager::SetDontCloseActiveMenu](#setdontcloseactivemenu)|Элементы управления ли `CContextMenuManager` закрывает активный контекстное меню, при отображении новой контекстное меню.|  
|[CContextMenuManager::ShowPopupMenu](#showpopupmenu)|Отображает указанное контекстное меню.|  
|[CContextMenuManager::TrackPopupMenu](#trackpopupmenu)|Отображает указанное контекстное меню. Возвращает индекс команды меню.|  
  
## <a name="remarks"></a>Примечания  
 `CContextMenuManager`Управляет контекстными меню и гарантирует, что они будут иметь согласованный вид.  
  
 Не следует создавать `CContextMenuManager` объекта вручную. Платформа приложения создает `CContextMenuManager` объекта. Тем не менее, следует вызывать [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) при инициализации приложения. После инициализации диспетчера контекста, используйте метод [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager) получить указатель на диспетчер контекста для вашего приложения.  
  
 Можно создать контекстные меню во время выполнения путем вызова `AddMenu`. Если вы хотите Показать меню без первого получения ввода данных пользователем, вызвать `ShowPopupMenu`. `TrackPopupMenu`используется для создания меню и ожидает ввода пользователя. `TrackPopupMenu`Возвращает индекс выбранной команды или 0, если пользователь завершил работу без выбора элементов.  
  
 `CContextMenuManager` Также можно сохранять и загружать свое состояние в реестр Windows.  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как добавить меню, `CContextMenuManager` объекта и как не удается закрыть активный во всплывающем меню при `CContextMenuManager` объекта отобразится новое всплывающее меню. Этот фрагмент кода является частью [пользовательские страницы образец](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages&#4;](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CContextMenuManager`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcontextmenumanager.h  
  
##  <a name="addmenu"></a>CContextMenuManager::AddMenu  
 Добавление контекстного меню, чтобы [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).  
  
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
 Ненулевое значение, если метод был выполнен успешно; 0, если происходит сбой метода.  
  
### <a name="remarks"></a>Примечания  
 Этот метод не выполняется, если `uiMenuResId` недопустим или если другое меню с тем же именем уже присутствует в `CContextMenuManager`.  
  
##  <a name="ccontextmenumanager"></a>CContextMenuManager::CContextMenuManager  
 Создает [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) объекта.  
  
```  
CContextMenuManager();
```  
  
### <a name="remarks"></a>Примечания  
 В большинстве случаев не следует создавать `CContextMenuManager` вручную. Платформа приложения создает `CContextMenuManager` объекта. Следует вызвать [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) во время инициализации приложения. Чтобы получить указатель диспетчера контекста, вызовите [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager).  
  
##  <a name="getmenubyid"></a>CContextMenuManager::GetMenuById  
 Возвращает дескриптор меню, связанного с идентификатором определенного ресурса.  
  
```  
HMENU GetMenuById(UINT nMenuResId) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nMenuResId`  
 Идентификатор ресурса для меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор связанным меню или `NULL` Если меню не найден.  
  
##  <a name="getmenubyname"></a>CContextMenuManager::GetMenuByName  
 Возвращает дескриптор для конкретного меню.  
  
```  
HMENU GetMenuByName(
    LPCTSTR lpszName,  
    UINT* puiOrigResID = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszName`  
 Строка, содержащая имя меню для извлечения.  
  
 [выходной] `puiOrigResID`  
 Указатель на `UINT`. Этот параметр содержит идентификатор ресурса для указанного меню, если найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор меню, которое совпадает с именем, указанным `lpszName`. `NULL`Если нет меню с именем `lpszName`.  
  
### <a name="remarks"></a>Примечания  
 Если этот метод находит меню, которое соответствует `lpszName`, `GetMenuByName` сохраняет идентификатор ресурса меню в параметре `puiOrigResID`.  
  
##  <a name="getmenunames"></a>CContextMenuManager::GetMenuNames  
 Возвращает список имен меню Добавить [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).  
  
```  
void GetMenuNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `listOfNames`  
 Ссылку на [CStringList](../../mfc/reference/cstringlist-class.md) параметр. Этот метод записывает список названий меню для этого параметра.  
  
##  <a name="loadstate"></a>CContextMenuManager::LoadState  
 Загружает сведения, связанные с [CContextMenuManager класса](../../mfc/reference/ccontextmenumanager-class.md) из реестра Windows.  
  
```  
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Строка, содержащая относительный путь раздела реестра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 `lpszProfileName` Параметр не абсолютный путь для записи реестра. Это относительный путь, который добавляется в конец раздела реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) и [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) соответственно.  
  
 Используйте метод [CContextMenuManager::SaveState](#savestate) сохранить контекстные меню в реестре.  
  
##  <a name="resetstate"></a>CContextMenuManager::ResetState  
 Удаляет все элементы из контекстных меню, связанные с [CContextMenuManager класса](../../mfc/reference/ccontextmenumanager-class.md).  
  
```  
virtual BOOL ResetState();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; `FALSE` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет всплывающие меню и удаляет их из `CContextMenuManager`.  
  
##  <a name="savestate"></a>CContextMenuManager::SaveState  
 Сохраняет сведения, связанные с [CContextMenuManager класса](../../mfc/reference/ccontextmenumanager-class.md) в реестре Windows.  
  
```  
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Строка, содержащая относительный путь раздела реестра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 `lpszProfileName` Параметр не абсолютный путь для записи реестра. Это относительный путь, который добавляется в конец раздела реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) и [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) соответственно.  
  
 Используйте метод [CContextMenuManager::LoadState](#loadstate) для загрузки контекстных меню из реестра.  
  
##  <a name="setdontcloseactivemenu"></a>CContextMenuManager::SetDontCloseActiveMenu  
 Элементы управления ли [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) закрывает active всплывающего меню, при отображении новой всплывающего меню.  
  
```  
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSet`  
 Логический параметр, который определяет, нужно ли закрыть активный во всплывающем меню. Значение `TRUE` указывает active во всплывающем меню не закрывается. `FALSE`Указывает, закрыта active во всплывающем меню.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `CContextMenuManager` закрывает активный во всплывающем меню.  
  
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
 Смещение по вертикали для контекстного меню в координатах клиента  
  
 [in] `pWndOwner`  
 Указатель на родительское окно в контекстном меню.  
  
 [in] `bOwnMessage`  
 Логический параметр, который указывает способ маршрутизации сообщений. Если `bOwnMessage` — `FALSE`, используется стандартный маршрут MFC. В противном случае — `pWndOwner` получает сообщения.  
  
 [in] `hmenuPopup`  
 Дескриптор меню, которое будет отображаться этот метод.  
  
 [in] `bAutoDestroy`  
 Логический параметр, указывающий, будет ли автоматически уничтожается меню.  
  
 [in] `bRightAlign`  
 Логический параметр, который указывает способ выравнивания элементов меню. Если `bRightAlign` — `TRUE`, меню по правому краю порядок чтения справа налево.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первая перегрузка метода возвращает ненулевое значение, если метод успешно; показано меню в противном случае — 0. Вторая перегрузка метода возвращает указатель на [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) Если в контекстном меню отображаются правильно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод похож на метод [CContextMenuManager::TrackPopupMenu](#trackpopupmenu) в том, что оба метода отображения контекстного меню. Тем не менее `TrackPopupMenu` возвращает индекс команды меню.  
  
 Если параметр `bAutoDestroy` — `FALSE`, необходимо вручную вызвать наследуемый `DestroyMenu` метод для освобождения ресурсов памяти. Реализация по умолчанию `ShowPopupMenu` , не используйте параметр `bAutoDestroy`. Он предоставляется для использования в будущем или для пользовательских классов, производных от `CContextMenuManager` класса.  
  
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
 Вертикальное смещение для контекстного меню в клиентских координатах.  
  
 [in] `pWndOwner`  
 Указатель на родительское окно в контекстном меню.  
  
 [in] `bRightAlign`  
 Логический параметр, который указывает способ выравнивания элементов меню. Если `bRightAlign` — `TRUE`, меню по правому краю порядок чтения справа налево. Если `bRightAlign` — `FALSE`, меню по левому краю порядок чтения справа налево.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор команды меню, команды, выбранные пользователем; 0, если пользователь закрывает контекстное меню без выбора команды меню.  
  
### <a name="remarks"></a>Примечания  
 Этот метод работает как модальное вызова для отображения контекстного меню. Приложение не будет продолжать следующая строка кода, пока пользователь закрывает контекстное меню или выбирает команду. Альтернативный метод, который можно использовать для отображения контекстного меню — [CContextMenuManager::ShowPopupMenu](#showpopupmenu). Этот метод не является модальным вызовом и не вернет идентификатор выбранной команды.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)

