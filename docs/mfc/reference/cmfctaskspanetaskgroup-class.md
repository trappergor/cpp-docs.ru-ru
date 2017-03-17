---
title: "Класс CMFCTasksPaneTaskGroup | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CMFCTasksPaneTaskGroup class
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
caps.latest.revision: 33
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
ms.openlocfilehash: 405a69a0c7d8c4179b36e1beec09fdfa7acd2d7b
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctaskspanetaskgroup-class"></a>Класс CMFCTasksPaneTaskGroup
`CMFCTasksPaneTaskGroup` Класс является вспомогательным классом, используемые [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) управления. Объекты типа `CMFCTasksPaneTaskGroup` представляют *группу задач*. Группа задач — это список элементов, отображаемых структурой в отдельном поле с кнопкой "Свернуть". Поле может иметь необязательный заголовок (имя группы). Если группа свернута, список задач не отображается.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCTasksPaneTaskGroup : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup](#cmfctaskspanetaskgroup)|Создает объект `CMFCTasksPaneTaskGroup`.|  
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::SetACCData](#setaccdata)|Определяет доступность данных для текущей группы задач.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::m_bIsBottom](#m_bisbottom)|Определяет, выравнивается ли группа задач в нижней части элемента управления области задач.|  
|[CMFCTasksPaneTaskGroup::m_bIsCollapsed](#m_biscollapsed)|Определяет, свернута ли группа задач.|  
|[CMFCTasksPaneTaskGroup::m_bIsSpecial](#m_bisspecial)|Определяет, является ли группа задач *специальные.* Платформа специальные заголовки отображаются разными цветами.|  
|[CMFCTasksPaneTaskGroup::m_lstTasks](#m_lsttasks)|Содержит список внутренних задач.|  
|[CMFCTasksPaneTaskGroup::m_rect](#m_rect)|Указывает ограничивающий прямоугольник заголовка группы.|  
|[CMFCTasksPaneTaskGroup::m_rectGroup](#m_rectgroup)|Указывает ограничивающий прямоугольник группы.|  
|[CMFCTasksPaneTaskGroup::m_strName](#m_strname)|Задает имя группы.|  
  
## <a name="remarks"></a>Примечания  
 На следующем рисунке показано группы расширенные задачи:  
  
 ![Развернутая группа задач](../../mfc/reference/media/nexttaskgrpexpand.png "nexttaskgrpexpand")  
  
 На следующем рисунке показано свернутая группа задач:  
  
 ![Свернутая группа задач](../../mfc/reference/media/nexttaskgrpcollapse.png "nexttaskgrpcollapse")  
  
 На следующем рисунке группа задач без заголовка:  
  
 ![Группа задач без заголовка](../../mfc/reference/media/nexttaskgrpnocapt.png "nexttaskgrpnocapt")  
  
 Ниже показаны две группы задач. Первой группы задач будет отмечен как специальный параметр `m_bIsSpecial` флаг `TRUE`, а вторая группа задач не является особенным. Обратите внимание, что заголовок для первой группы задач темнее второй группы задач:  
  
 ![Специальная группа задач](../../mfc/reference/media/nexttaskgrpspecial.png "nexttaskgrpspecial")  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxTasksPane.h  
  
##  <a name="cmfctaskspanetaskgroup"></a>CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup  
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
 Указывает имя группы в заголовок группы.  
  
 `bIsBottom`  
 Указывает, выравнивается ли группу в нижнюю часть элемента управления области задач.  
  
 `bIsSpecial`  
 Указывает, назначается ли группа *специальных* и таким образом, является ли название группы заполняется другим цветом.  
  
 `bIsCollapsed`  
 Указывает, является ли группа свернута.  
  
 `pPage`  
 Задает страницу свойств, к которой принадлежит эта группа задач.  
  
 `hIcon`  
 Задает значок, отображаемый в заголовке группы.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_bisbottom"></a>CMFCTasksPaneTaskGroup::m_bIsBottom  
 Определяет, выравнивается ли группа задач в нижней части элемента управления области задач.  
  
```  
BOOL m_bIsBottom;  
```  
  
### <a name="remarks"></a>Примечания  
 Только одна группа может быть выровнен по нижней части элемента управления области задач. Эта группа задач должны быть добавлены последнего. Дополнительные сведения см. в разделе [CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).  
  
##  <a name="m_biscollapsed"></a>CMFCTasksPaneTaskGroup::m_bIsCollapsed  
 Определяет, свернута ли группа задач.  
  
```  
BOOL m_bIsCollapsed;  
```  
  
### <a name="remarks"></a>Примечания  
 Можно включить или отключить возможность свернуть группы в области задач путем вызова [CMFCTasksPane::EnableGroupCollapse](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse).  
  
##  <a name="m_bisspecial"></a>CMFCTasksPaneTaskGroup::m_bIsSpecial  
 Определяет, является ли группа задач *специальных* и ли заголовок специальная группа задач должна быть определена с другим цветом.  
  
```  
BOOL m_bIsSpecial;  
```  
  
### <a name="remarks"></a>Примечания  
 Если приложение использует визуальной темы Windows XP и `m_bIsSpecial` — `FALSE`, платформа вызывает функцию `DrawThemeBackground` с `EBP_NORMALGROUPBACKGROUND` флаг. Если `m_bIsSpecial` — `TRUE`, платформа вызывает функцию `DrawThemeBackground` с `EBP_SPECIALGROUPBACKGROUND` флаг.  
  
##  <a name="m_lsttasks"></a>CMFCTasksPaneTaskGroup::m_lstTasks  
 Содержит список внутренних задач.  
  
```  
CObList m_lstTasks;  
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы заполнить этот список, вызовите [CMFCTasksPane::AddTask](../../mfc/reference/cmfctaskspane-class.md#addtask).  
  
##  <a name="m_rect"></a>CMFCTasksPaneTaskGroup::m_rect  
 Указывает ограничивающий прямоугольник заголовка группы.  
  
```  
CRect m_rect;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение вычисляется автоматически платформой.  
  
##  <a name="m_rectgroup"></a>CMFCTasksPaneTaskGroup::m_rectGroup  
 Указывает ограничивающий прямоугольник группы.  
  
```  
CRect m_rectGroup;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение вычисляется автоматически платформой.  
  
##  <a name="m_strname"></a>CMFCTasksPaneTaskGroup::m_strName  
 Задает имя группы.  
  
```  
CString m_strName;  
```  
  
### <a name="remarks"></a>Примечания  
 Если это значение является пустым, название группы не отображается и не удается свернуть группу.  
  
##  <a name="setaccdata"></a>CMFCTasksPaneTaskGroup::SetACCData  
 Определяет доступность данных для текущей группы задач.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParent`  
 Представляет окно родительской группы задач.  
  
 [выходной] `data`  
 Объект типа `CAccessibilityData` , заполняется данными специальные группы задач.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если `data` параметр был заполнен данными специальные группы задач успешно, в противном случае — `FALSE`.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)   
 [Класс CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)   
 [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)

