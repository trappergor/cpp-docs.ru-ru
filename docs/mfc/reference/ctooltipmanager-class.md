---
title: "Класс CTooltipManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTooltipManager
dev_langs:
- C++
helpviewer_keywords:
- CTooltipManager class
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
caps.latest.revision: 22
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
ms.openlocfilehash: 3bbf191aacdd318f2afb0bd1a126c3eff290fad6
ms.lasthandoff: 02/24/2017

---
# <a name="ctooltipmanager-class"></a>Класс CTooltipManager
Хранит сведения среды выполнения о подсказках. Экземпляр класса `CTooltipManager` создается один раз для каждого приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CTooltipManager : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTooltipManager::CreateToolTip](#createtooltip)|Создает элемент управления "Всплывающая подсказка" для указанных типов  элементов управления Windows.|  
|[CTooltipManager::DeleteToolTip](#deletetooltip)|Удаляет элемент управления "Всплывающая подсказка".|  
|[CTooltipManager::SetTooltipParams](#settooltipparams)|Настраивает внешний вид элемента управления "Всплывающая подсказка" для указанных типов элементов управления Windows.|  
|[CTooltipManager::SetTooltipText](#settooltiptext)|Задает текст и описание для элемента управления "Всплывающая подсказка".|  
|[CTooltipManager::UpdateTooltips](#updatetooltips)||  
  
## <a name="remarks"></a>Примечания  
 Используйте [от CMFCToolTipCtrl класс](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, и `CTooltipManager` вместе, чтобы реализовать настраиваемый всплывающих подсказок в приложении. Пример использования этих классов подсказки в разделе [от CMFCToolTipCtrl класс](../../mfc/reference/cmfctooltipctrl-class.md) раздела.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtooltipmanager.h  
  
##  <a name="a-namecreatetooltipa--ctooltipmanagercreatetooltip"></a><a name="createtooltip"></a>CTooltipManager::CreateToolTip  
 Создает элемент управления всплывающей подсказки.  
  
```  
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,  
    CWnd* pWndParent,  
    UINT nType);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `pToolTip`  
 Ссылка на указатель всплывающей подсказки. Ему присваивается выберите только что созданный всплывающей подсказки при возврате из функции.  
  
 [in] `pWndParent`  
 Родительский объект подсказки.  
  
 [in] `nType`  
 Тип всплывающей подсказки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если подсказка был успешно создан.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [CTooltipManager::DeleteToolTip](#deletetooltip) для удаления элемента управления всплывающей подсказки, который передается обратно в `pToolTip`.  
  
 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) тип, который задает параметры визуального отображения каждой всплывающей подсказки, он создает в зависимости от подсказки `nType` указывает. Чтобы изменить параметры для одного или нескольких типов всплывающей подсказки, вызовите [CTooltipManager::SetTooltipParams](#settooltipparams).  
  
 Подсказка допустимые типы перечислены в следующей таблице.  
  
|ToolTip-тип|Категория элемента|Примеры типов|  
|------------------|----------------------|-------------------|  
|AFX_TOOLTIP_TYPE_BUTTON|Кнопка.|CMFCButton|  
|AFX_TOOLTIP_TYPE_CAPTIONBAR|Заголовок.|CMFCCaptionBar|  
|AFX_TOOLTIP_TYPE_DEFAULT|Любой элемент управления, которое не помещается в другую категорию.|Отсутствует.|  
|AFX_TOOLTIP_TYPE_DOCKBAR|Закрепляемая область.|CDockablePane|  
|AFX_TOOLTIP_TYPE_EDIT|Текстовое поле.|Отсутствует.|  
|AFX_TOOLTIP_TYPE_MINIFRAME|Области.|CPaneFrameWnd|  
|AFX_TOOLTIP_TYPE_PLANNER|Планировщик.|Отсутствует.|  
|AFX_TOOLTIP_TYPE_RIBBON|В области ленты.|CMFCRibbonBar CMFCRibbonPanelMenuBar|  
|AFX_TOOLTIP_TYPE_TAB|Набор вкладок.|CMFCTabCtrl|  
|AFX_TOOLTIP_TYPE_TOOLBAR|Панель инструментов.|CMFCToolBar CMFCPopupMenuBar|  
|AFX_TOOLTIP_TYPE_TOOLBOX|Панель элементов.|Отсутствует.|  
  
##  <a name="a-namedeletetooltipa--ctooltipmanagerdeletetooltip"></a><a name="deletetooltip"></a>CTooltipManager::DeleteToolTip  
 Удаляет элемент управления "Всплывающая подсказка".  
  
```  
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `pToolTip`  
 Ссылка на указатель подсказки будут уничтожены.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для каждого [CToolTipCtrl-класс](../../mfc/reference/ctooltipctrl-class.md) , созданного с [CTooltipManager::CreateToolTip](#createtooltip). Родительский элемент управления должен вызывать этот метод из его `OnDestroy` обработчика. Это необходимо для правильного удаления подсказки от платформы. Этот метод задает `pToolTip` для `NULL` перед возвратом.  
  
##  <a name="a-namesettooltipparamsa--ctooltipmanagersettooltipparams"></a><a name="settooltipparams"></a>CTooltipManager::SetTooltipParams  
 Настраивает внешний вид элемента управления всплывающей подсказки для указанного типов элементов управления Windows.  
  
```  
void SetTooltipParams(
    UINT nTypes,  
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),  
    CMFCToolTipInfo* pParams=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nTypes`  
 Указывает типы элементов управления.  
  
 [in] `pRTC`  
 Класс среды выполнения всплывающая подсказка.  
  
 [in] `pParams`  
 Параметры всплывающей подсказки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод задает класс среды выполнения и начальные параметры, [CToolTipManager](../../mfc/reference/ctooltipmanager-class.md) использует при создании всплывающих подсказок. Когда элемент управления вызывает [CTooltipManager::CreateToolTip](#createtooltip) и передает в подсказке типа, один из типов, обозначенными `nTypes`, диспетчер подсказки создает элемент управления всплывающей подсказки, который является экземпляром класса среды выполнения, указанного `pRTC` и передает параметры, определенные `pParams` для создаваемой подсказки.  
  
 При вызове этого метода, все существующие владельцы подсказки сообщение AFX_WM_UPDATETOOLTIPS и их необходимо повторно создать их подсказки с помощью [CTooltipManager::CreateToolTip](#createtooltip).  
  
 `nTypes`может быть любое сочетание допустимых подсказки типы, [CTooltipManager::CreateToolTip](#createtooltip) использует или он может быть AFX_TOOLTIP_TYPE_ALL. Если передать AFX_TOOLTIP_TYPE_ALL затрагиваются все типы всплывающей подсказки.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `SetTooltipParams` метод `CTooltipManager` класса. Этот фрагмент кода является частью [пример рисования клиента](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient&11;](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]  
  
##  <a name="a-namesettooltiptexta--ctooltipmanagersettooltiptext"></a><a name="settooltiptext"></a>CTooltipManager::SetTooltipText  
 Задает текст и описание для всплывающей подсказки.  
  
```  
static void SetTooltipText(
    TOOLINFO* pTI,  
    CToolTipCtrl* pToolTip,  
    UINT nType,  
    const CString strText,  
    LPCTSTR lpszDescr=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pTI`  
 Указатель на объект TOOLINFO.  
  
 [in, out] `pToolTip`  
 Указатель на элемент управления всплывающей подсказки, для которого требуется задать текст и описание.  
  
 [in] `nType`  
 Указывает тип элемента управления, с которым связан этот всплывающей подсказки.  
  
 [in] `strText`  
 Текст, чтобы задать как текст подсказки.  
  
 [in] `lpszDescr`  
 Указатель на описание всплывающей подсказки. Может быть `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Значение `nType` должно быть то же значение, что `nType` параметр [CTooltipManager::CreateToolTip](#createtooltip) при создании всплывающей подсказки.  
  
##  <a name="a-nameupdatetooltipsa--ctooltipmanagerupdatetooltips"></a><a name="updatetooltips"></a>CTooltipManager::UpdateTooltips  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void UpdateTooltips();
```  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс от CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)   
 [Класс CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)

