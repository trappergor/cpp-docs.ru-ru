---
title: Класс CMFCTasksPaneTask | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCTasksPaneTask [MFC], CMFCTasksPaneTask
- CMFCTasksPaneTask [MFC], SetACCData
- CMFCTasksPaneTask [MFC], m_bAutoDestroyWindow
- CMFCTasksPaneTask [MFC], m_bIsBold
- CMFCTasksPaneTask [MFC], m_dwUserData
- CMFCTasksPaneTask [MFC], m_hwndTask
- CMFCTasksPaneTask [MFC], m_nIcon
- CMFCTasksPaneTask [MFC], m_nWindowHeight
- CMFCTasksPaneTask [MFC], m_pGroup
- CMFCTasksPaneTask [MFC], m_rect
- CMFCTasksPaneTask [MFC], m_strName
- CMFCTasksPaneTask [MFC], m_uiCommandID
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4008389121a1a78ca746798af7f3fc18c9663b93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371336"
---
# <a name="cmfctaskspanetask-class"></a>Класс CMFCTasksPaneTask
`CMFCTasksPaneTask` Класс представляет вспомогательный класс, представляющий задачи для элемента управления области задач ( [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)). Объект задач представляет элемент в группе задач ( [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)). Каждая задача может иметь команду, которую платформа выполняет, когда пользователь щелкает задачу, и значок, который присутствует слева от имени задачи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCTasksPaneTask : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCTasksPaneTask::CMFCTasksPaneTask](#cmfctaskspanetask)|Создает и инициализирует `CMFCTasksPaneTask` объекта.|  
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCTasksPaneTask::SetACCData](#setaccdata)|Определяет, какие данные специальных возможностей для текущей задачи.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание|  
|----------|-----------------|  
|[CMFCTasksPaneTask::m_bAutoDestroyWindow](#m_bautodestroywindow)|Определяет, является ли окно «Задача», автоматически освобождается.|  
|[CMFCTasksPaneTask::m_bIsBold](#m_bisbold)|Определяет, рисуется ли платформа метка задачи полужирным шрифтом.|  
|[CMFCTasksPaneTask::m_dwUserData](#m_dwuserdata)|Содержит определяемые пользователем данные, которые платформа связывает с задачей. Равен нулю, если задача не содержит связанных данных.|  
|[CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)|Дескриптор окна задач.|  
|[CMFCTasksPaneTask::m_nIcon](#m_nicon)|Индекс в списке изображений, изображения, платформа отображает рядом с задачей.|  
|[CMFCTasksPaneTask::m_nWindowHeight](#m_nwindowheight)|Высота окна задач. Если задача не имеет задач окна, это значение равно нулю.|  
|[CMFCTasksPaneTask::m_pGroup](#m_pgroup)|Указатель на `CMFCTasksPaneTaskGroup` , к которой принадлежит эта задача.|  
|[CMFCTasksPaneTask::m_rect](#m_rect)|Указывает ограничивающий прямоугольник задачи.|  
|[CMFCTasksPaneTask::m_strName](#m_strname)|Имя задачи.|  
|[CMFCTasksPaneTask::m_uiCommandID](#m_uicommandid)|Указывает идентификатор команды, которую платформа выполняет, когда пользователь щелкает задачу. Если это значение не является допустимой командой Идентификатором, задача рассматривается как простая метка.|  
  
## <a name="remarks"></a>Примечания  
 На следующем рисунке группа задач, который содержит три задачи:  
  
 ![Развернутая группа задач](../../mfc/reference/media/nexttaskgrpexpand.png "nexttaskgrpexpand")  
  
> [!NOTE]
>  Если задача не имеет идентификатор допустимой команды, он рассматривается как простая метка.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxTasksPane.h  
  
##  <a name="cmfctaskspanetask"></a>  CMFCTasksPaneTask::CMFCTasksPaneTask  
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
 Указывает индекс изображения задачи в списке изображений.  
  
 `uiCommandID`  
 Указывает идентификатор команды команду, которая выполняется при щелчке задачи.  
  
 `dwUserData`  
 Определенные пользователем данные.  
  
 `hwndTask`  
 Указывает дескриптор окна задач.  
  
 `bAutoDestroyWindow`  
 Если `TRUE`, окно «Задача» будет удален автоматически.  
  
 `nWindowHeight`  
 Указывает высоту окна задач.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_bautodestroywindow"></a>  CMFCTasksPaneTask::m_bAutoDestroyWindow  
 Определяет, является ли окно «Задача», автоматически освобождается.  
  
```  
BOOL m_bAutoDestroyWindow;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение `TRUE` позволяет указать, что окно задач ( [CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)) автоматически; в противном случае следует удалить `FALSE`.  
  
##  <a name="m_bisbold"></a>  CMFCTasksPaneTask::m_bIsBold  
 Определяет, выводится ли метка задачи полужирным шрифтом.  
  
```  
BOOL m_bIsBold;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этого элемента `TRUE` для отображения полужирного текста для метки задачи.  
  
##  <a name="m_dwuserdata"></a>  CMFCTasksPaneTask::m_dwUserData  
 Содержит определяемые пользователем данные, связанный с задачей. Равен нулю, если данные не связан с задачей.  
  
```  
DWORD m_dwUserData;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_hwndtask"></a>  CMFCTasksPaneTask::m_hwndTask  
 Дескриптор окна задач.  
  
```  
HWND m_hwndTask;  
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы добавить окно задач, вызовите [CMFCTasksPane::AddWindow](../../mfc/reference/cmfctaskspane-class.md#addwindow).  
  
##  <a name="m_nicon"></a>  CMFCTasksPaneTask::m_nIcon  
 Индекс позиции в списке изображений, определяющий изображение, отображаемое рядом с указанной задачи.  
  
```  
int m_nIcon;  
```  
  
### <a name="remarks"></a>Примечания  
 Список изображений задается [CMFCTasksPane::SetIconsList](../../mfc/reference/cmfctaskspane-class.md#seticonslist).  
  
 Задать `m_nIcon` значение -1, если требуется отобразить задачи без изображения.  
  
##  <a name="m_nwindowheight"></a>  CMFCTasksPaneTask::m_nWindowHeight  
 Высота окна задач. Если задача не имеет задач окна, это значение равно нулю.  
  
```  
int m_nWindowHeight;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_pgroup"></a>  CMFCTasksPaneTask::m_pGroup  
 Указатель на [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) , которому принадлежит эта задача.  
  
```  
CMFCTasksPaneTaskGroup* m_pGroup;  
```  
  
### <a name="remarks"></a>Примечания  
 Каждая задача должна быть родительская группа. Добавить группы в области задач путем вызова [CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).  
  
##  <a name="m_rect"></a>  CMFCTasksPaneTask::m_rect  
 Указывает ограничивающий прямоугольник задачи.  
  
```  
CRect m_rect;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение вычисляется платформой при рисовании задачи.  
  
##  <a name="m_strname"></a>  CMFCTasksPaneTask::m_strName  
 Имя задачи.  
  
```  
CString m_strName;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_uicommandid"></a>  CMFCTasksPaneTask::m_uiCommandID  
 Указывает идентификатор команды команду, которая выполняется, когда пользователь щелкает задачу. Если это значение не является допустимой командой Идентификатором, задача рассматривается как простая метка.  
  
```  
UINT m_uiCommandID;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setaccdata"></a>  CMFCTasksPaneTask::SetACCData  
 Определяет, какие данные специальных возможностей для текущей задачи.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParent`  
 Представляет родительское окно текущей задачи.  
  
 [выходной] `data`  
 Объект типа `CAccessibilityData` заполняется данные специальных возможностей текущей задачи.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если `data` параметр был успешно заполненная данные специальных возможностей текущей задачи; в противном случае — `FALSE`.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CObject](../../mfc/reference/cobject-class.md)
