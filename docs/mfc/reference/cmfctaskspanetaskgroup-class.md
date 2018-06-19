---
title: Класс CMFCTasksPaneTaskGroup | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsBottom
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsCollapsed
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsSpecial
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_lstTasks
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rect
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rectGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_strName
dev_langs:
- C++
helpviewer_keywords:
- CMFCTasksPaneTaskGroup [MFC], CMFCTasksPaneTaskGroup
- CMFCTasksPaneTaskGroup [MFC], SetACCData
- CMFCTasksPaneTaskGroup [MFC], m_bIsBottom
- CMFCTasksPaneTaskGroup [MFC], m_bIsCollapsed
- CMFCTasksPaneTaskGroup [MFC], m_bIsSpecial
- CMFCTasksPaneTaskGroup [MFC], m_lstTasks
- CMFCTasksPaneTaskGroup [MFC], m_rect
- CMFCTasksPaneTaskGroup [MFC], m_rectGroup
- CMFCTasksPaneTaskGroup [MFC], m_strName
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d51b29f9ea2719f98f263565680ded2360197572
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370849"
---
# <a name="cmfctaskspanetaskgroup-class"></a>Класс CMFCTasksPaneTaskGroup
`CMFCTasksPaneTaskGroup` Класс — это вспомогательный класс, используемый [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) управления. Объекты типа `CMFCTasksPaneTaskGroup` представляют *группу задач*. Группа задач — это список элементов, отображаемых структурой в отдельном поле с кнопкой "Свернуть". Поле может иметь необязательный заголовок (имя группы). Если группа свернута, список задач не отображается.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCTasksPaneTaskGroup : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup](#cmfctaskspanetaskgroup)|Создает объект `CMFCTasksPaneTaskGroup`.|  
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::SetACCData](#setaccdata)|Определяет, какие данные специальных возможностей для текущей группы задач.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::m_bIsBottom](#m_bisbottom)|Определяет, является ли группа задач выравнивается по нижней части элемента управления области задач.|  
|[CMFCTasksPaneTaskGroup::m_bIsCollapsed](#m_biscollapsed)|Определяет, свернута ли группа задач.|  
|[CMFCTasksPaneTaskGroup::m_bIsSpecial](#m_bisspecial)|Определяет, является ли группа задач *специальные.* Платформа отображает специальные заголовки разными цветами.|  
|[CMFCTasksPaneTaskGroup::m_lstTasks](#m_lsttasks)|Содержит внутреннего списка задач.|  
|[CMFCTasksPaneTaskGroup::m_rect](#m_rect)|Указывает ограничивающий прямоугольник заголовка группы.|  
|[CMFCTasksPaneTaskGroup::m_rectGroup](#m_rectgroup)|Указывает ограничивающий прямоугольник группы.|  
|[CMFCTasksPaneTaskGroup::m_strName](#m_strname)|Задает имя группы.|  
  
## <a name="remarks"></a>Примечания  
 На следующем рисунке показана группа расширенные задачи:  
  
 ![Развернутая группа задач](../../mfc/reference/media/nexttaskgrpexpand.png "nexttaskgrpexpand")  
  
 На следующем рисунке показано свернутая группа задач:  
  
 ![Свернутая группа задач](../../mfc/reference/media/nexttaskgrpcollapse.png "nexttaskgrpcollapse")  
  
 На следующем рисунке показано группа задач без заголовка:  
  
 ![Группа задач без заголовка](../../mfc/reference/media/nexttaskgrpnocapt.png "nexttaskgrpnocapt")  
  
 На следующем рисунке показаны две группы задач. Первая группа задач, задав помечен как специальные `m_bIsSpecial` флаг `TRUE`, а вторая группа задач не является особенным. Обратите внимание, как заголовок для первой группы задач темного, чем второй группы задач:  
  
 ![Специальная группа задач](../../mfc/reference/media/nexttaskgrpspecial.png "nexttaskgrpspecial")  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxTasksPane.h  
  
##  <a name="cmfctaskspanetaskgroup"></a>  CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup  
 Создает объект `CMFCTasksPaneTaskGroup`.  
  
```  
CMFCTasksPaneTaskGroup(
    LPCTSTR lpszName,  
    BOOL bIsBottom,  
    BOOL bIsSpecial=FALSE,  
    BOOL bIsCollapsed=FALSE,  
    CMFCTasksPanePropertyPage* pPage=NULL,  
    HICON hIcon=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Указывает имя группы в заголовке группы.  
  
 `bIsBottom`  
 Указывает ли группе выравнивается относительно нижней части элемента управления области задач.  
  
 `bIsSpecial`  
 Указывает, является ли группа используется в качестве *специальные* , и таким образом, является ли название группы заполняется другим цветом.  
  
 `bIsCollapsed`  
 Указывает, является ли группа свернута.  
  
 `pPage`  
 Указывает страницу свойств, к которой принадлежит эта группа задач.  
  
 `hIcon`  
 Задает значок, отображаемый в заголовке группы.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_bisbottom"></a>  CMFCTasksPaneTaskGroup::m_bIsBottom  
 Определяет, является ли группа задач выравнивается по нижней части элемента управления области задач.  
  
```  
BOOL m_bIsBottom;  
```  
  
### <a name="remarks"></a>Примечания  
 Только одна группа может быть выровнен по нижней части элемента управления области задач. Последний необходимо добавить эту группу задач. Дополнительные сведения см. в разделе [CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).  
  
##  <a name="m_biscollapsed"></a>  CMFCTasksPaneTaskGroup::m_bIsCollapsed  
 Определяет, свернута ли группа задач.  
  
```  
BOOL m_bIsCollapsed;  
```  
  
### <a name="remarks"></a>Примечания  
 Можно включить или отключить возможность свертывания групп в области задач путем вызова [CMFCTasksPane::EnableGroupCollapse](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse).  
  
##  <a name="m_bisspecial"></a>  CMFCTasksPaneTaskGroup::m_bIsSpecial  
 Определяет, является ли группа задач *специальные* и ли заголовок специальная группа задач должна быть определена с другим цветом.  
  
```  
BOOL m_bIsSpecial;  
```  
  
### <a name="remarks"></a>Примечания  
 Если приложение использует тему Windows XP и `m_bIsSpecial` — `FALSE`, платформа вызывает `DrawThemeBackground` с `EBP_NORMALGROUPBACKGROUND` флаг. Если `m_bIsSpecial` — `TRUE`, платформа вызывает `DrawThemeBackground` с `EBP_SPECIALGROUPBACKGROUND` флаг.  
  
##  <a name="m_lsttasks"></a>  CMFCTasksPaneTaskGroup::m_lstTasks  
 Содержит внутреннего списка задач.  
  
```  
CObList m_lstTasks;  
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы заполнить этот список, вызовите [CMFCTasksPane::AddTask](../../mfc/reference/cmfctaskspane-class.md#addtask).  
  
##  <a name="m_rect"></a>  CMFCTasksPaneTaskGroup::m_rect  
 Указывает ограничивающий прямоугольник заголовка группы.  
  
```  
CRect m_rect;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение вычисляется автоматически платформой.  
  
##  <a name="m_rectgroup"></a>  CMFCTasksPaneTaskGroup::m_rectGroup  
 Указывает ограничивающий прямоугольник группы.  
  
```  
CRect m_rectGroup;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение вычисляется автоматически платформой.  
  
##  <a name="m_strname"></a>  CMFCTasksPaneTaskGroup::m_strName  
 Задает имя группы.  
  
```  
CString m_strName;  
```  
  
### <a name="remarks"></a>Примечания  
 Если это значение является пустым, заголовка группы не отображается и не могут быть свернуты группы.  
  
##  <a name="setaccdata"></a>  CMFCTasksPaneTaskGroup::SetACCData  
 Определяет, какие данные специальных возможностей для текущей группы задач.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParent`  
 Представляет окно родительской группы задач.  
  
 [выходной] `data`  
 Объект типа `CAccessibilityData` заполняется данные специальных возможностей текущей группы задач.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если `data` параметр был успешно заполненная данные специальных возможностей текущей группы задач; в противном случае — `FALSE`.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)   
 [Класс CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)   
 [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)   
 [Класс CObject](../../mfc/reference/cobject-class.md)
