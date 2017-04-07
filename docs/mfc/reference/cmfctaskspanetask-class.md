---
title: "Класс CMFCTasksPaneTask | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTask::m_bAutoDestroyWindow
- AFXTASKSPANE/CMFCTasksPaneTask::m_bIsBold
- AFXTASKSPANE/CMFCTasksPaneTask::m_dwUserData
- AFXTASKSPANE/CMFCTasksPaneTask::m_hwndTask
- AFXTASKSPANE/CMFCTasksPaneTask::m_nIcon
- AFXTASKSPANE/CMFCTasksPaneTask::m_nWindowHeight
- AFXTASKSPANE/CMFCTasksPaneTask::m_pGroup
- AFXTASKSPANE/CMFCTasksPaneTask::m_rect
- AFXTASKSPANE/CMFCTasksPaneTask::m_strName
- AFXTASKSPANE/CMFCTasksPaneTask::m_uiCommandID
dev_langs:
- C++
helpviewer_keywords:
- CMFCTasksPaneTask class
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
caps.latest.revision: 27
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
ms.openlocfilehash: 20713b45c4b6aadc5cdfeaadb6ed269aaf7b337f
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctaskspanetask-class"></a>Класс CMFCTasksPaneTask
`CMFCTasksPaneTask` Класс является вспомогательным классом, представляющий задачи для элемента управления области задач ( [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)). Объект задач представляет элемент в группе задач ( [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)). Каждая задача может иметь команду, которую платформа выполняет, когда пользователь щелкает задачу, и значок, который присутствует слева от имени задачи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCTasksPaneTask : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCTasksPaneTask::CMFCTasksPaneTask](#cmfctaskspanetask)|Создает и инициализирует `CMFCTasksPaneTask` объекта.|  
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCTasksPaneTask::SetACCData](#setaccdata)|Определяет доступность данных для текущей задачи.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCTasksPaneTask::m_bAutoDestroyWindow](#m_bautodestroywindow)|Определяет, окно «Задача» она автоматически уничтожается.|  
|[CMFCTasksPaneTask::m_bIsBold](#m_bisbold)|Определяет, рисуется ли платформа метка задачи полужирным шрифтом.|  
|[CMFCTasksPaneTask::m_dwUserData](#m_dwuserdata)|Содержит определяемые пользователем данные, которые платформа связывает с задачей. Если задача не содержит связанных данных имеет нулевое значение.|  
|[CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)|Дескриптор окна задач.|  
|[CMFCTasksPaneTask::m_nIcon](#m_nicon)|Индекс в списке изображений к изображению, отображаемому платформа рядом с задачей.|  
|[CMFCTasksPaneTask::m_nWindowHeight](#m_nwindowheight)|Высота окна задач. Если задача не имеет задач окна, это значение равно нулю.|  
|[CMFCTasksPaneTask::m_pGroup](#m_pgroup)|Указатель на `CMFCTasksPaneTaskGroup` , к которому принадлежит эта задача.|  
|[CMFCTasksPaneTask::m_rect](#m_rect)|Указывает ограничивающий прямоугольник задачи.|  
|[CMFCTasksPaneTask::m_strName](#m_strname)|Имя задачи.|  
|[CMFCTasksPaneTask::m_uiCommandID](#m_uicommandid)|Указывает идентификатор команды, команды, которую платформа выполняет, когда пользователь щелкает задачу. Если это значение не является допустимой командой Идентификатором, задача рассматривается как простой метки.|  
  
## <a name="remarks"></a>Примечания  
 На следующем рисунке показано группе задач, который содержит три задачи:  
  
 ![Развернутая группа задач](../../mfc/reference/media/nexttaskgrpexpand.png "nexttaskgrpexpand")  
  
> [!NOTE]
>  Если задача не имеет идентификатор допустимая команда, считается простой метки.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxTasksPane.h  
  
##  <a name="cmfctaskspanetask"></a>CMFCTasksPaneTask::CMFCTasksPaneTask  
 Создает и инициализирует `CMFCTasksPaneTask` объекта.  
  
```  
CMFCTasksPaneTask(
    CMFCTasksPaneTaskGroup* pGroup,  
    LPCTSTR lpszName,  
    int nIcon,  
    UINT uiCommandID,  
    DWORD dwUserData = 0,  
    HWND hwndTask = NULL,  
    BOOL bAutoDestroyWindow = FALSE,  
    int nWindowHeight = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `pGroup`  
 Указывает [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) , которому принадлежит задача.  
  
 `lpszName`  
 Задает имя задачи.  
  
 `nIcon`  
 Указывает индекс образа задачи в списке изображений.  
  
 `uiCommandID`  
 Указывает команду, которая выполняется при щелчке задачи идентификатор команды.  
  
 `dwUserData`  
 Определенные пользователем данные.  
  
 `hwndTask`  
 Указывает дескриптор окна задач.  
  
 `bAutoDestroyWindow`  
 Если `TRUE`, окно «Задача» будет автоматически уничтожен.  
  
 `nWindowHeight`  
 Указывает высоту окна задач.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_bautodestroywindow"></a>CMFCTasksPaneTask::m_bAutoDestroyWindow  
 Определяет, окно «Задача» она автоматически уничтожается.  
  
```  
BOOL m_bAutoDestroyWindow;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение `TRUE` указать, что окно «Задача» ( [CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)) следует уничтожить автоматически; в противном случае — `FALSE`.  
  
##  <a name="m_bisbold"></a>CMFCTasksPaneTask::m_bIsBold  
 Определяет, выводится ли метка задачи полужирным шрифтом.  
  
```  
BOOL m_bIsBold;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этого элемента `TRUE` для отображения полужирный текст метки задачи.  
  
##  <a name="m_dwuserdata"></a>CMFCTasksPaneTask::m_dwUserData  
 Содержит определяемые пользователем данные, связанные с задачей. Если данные не связан с задачей имеет нулевое значение.  
  
```  
DWORD m_dwUserData;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_hwndtask"></a>CMFCTasksPaneTask::m_hwndTask  
 Дескриптор окна задач.  
  
```  
HWND m_hwndTask;  
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы добавить окно задач, вызовите [CMFCTasksPane::AddWindow](../../mfc/reference/cmfctaskspane-class.md#addwindow).  
  
##  <a name="m_nicon"></a>CMFCTasksPaneTask::m_nIcon  
 Индекс позиции в списке изображений, определяющий изображение, которое отображается рядом с указанной задачи.  
  
```  
int m_nIcon;  
```  
  
### <a name="remarks"></a>Примечания  
 Список изображений задается [CMFCTasksPane::SetIconsList](../../mfc/reference/cmfctaskspane-class.md#seticonslist).  
  
 Задайте `m_nIcon` значение -1, если требуется отобразить задачи без изображения.  
  
##  <a name="m_nwindowheight"></a>CMFCTasksPaneTask::m_nWindowHeight  
 Высота окна задач. Если задача не имеет задач окна, это значение равно нулю.  
  
```  
int m_nWindowHeight;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_pgroup"></a>CMFCTasksPaneTask::m_pGroup  
 Указатель на [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) , которому принадлежит эта задача.  
  
```  
CMFCTasksPaneTaskGroup* m_pGroup;  
```  
  
### <a name="remarks"></a>Примечания  
 Все задачи должны содержать родительской группы. Добавить группы в области задач с помощью [CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).  
  
##  <a name="m_rect"></a>CMFCTasksPaneTask::m_rect  
 Указывает ограничивающий прямоугольник задачи.  
  
```  
CRect m_rect;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение рассчитывается средой при рисовании задачи.  
  
##  <a name="m_strname"></a>CMFCTasksPaneTask::m_strName  
 Имя задачи.  
  
```  
CString m_strName;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_uicommandid"></a>CMFCTasksPaneTask::m_uiCommandID  
 Указывает команду, которая выполняется, когда пользователь щелкает задачу идентификатор команды. Если это значение не является допустимой командой Идентификатором, задача рассматривается как простой метки.  
  
```  
UINT m_uiCommandID;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setaccdata"></a>CMFCTasksPaneTask::SetACCData  
 Определяет доступность данных для текущей задачи.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParent`  
 Представляет родительского окна текущей задачи.  
  
 [выходной] `data`  
 Объект типа `CAccessibilityData` , заполняется данными специальных возможностей текущей задачи.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если `data` параметр был заполнен данными специальных возможностей текущей задачи успешно, в противном случае — `FALSE`.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)

