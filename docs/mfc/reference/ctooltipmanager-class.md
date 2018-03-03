---
title: "Класс CTooltipManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager::CreateToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::DeleteToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipParams
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipText
- AFXTOOLTIPMANAGER/CTooltipManager::UpdateTooltips
dev_langs:
- C++
helpviewer_keywords:
- CTooltipManager [MFC], CreateToolTip
- CTooltipManager [MFC], DeleteToolTip
- CTooltipManager [MFC], SetTooltipParams
- CTooltipManager [MFC], SetTooltipText
- CTooltipManager [MFC], UpdateTooltips
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2adb62f107cb50ade529d552ce1735c57f74b171
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ctooltipmanager-class"></a>Класс CTooltipManager
Хранит сведения среды выполнения о подсказках. Экземпляр класса `CTooltipManager` создается один раз для каждого приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CTooltipManager : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CTooltipManager::CreateToolTip](#createtooltip)|Создает элемент управления "Всплывающая подсказка" для указанных типов  элементов управления Windows.|  
|[CTooltipManager::DeleteToolTip](#deletetooltip)|Удаляет элемент управления "Всплывающая подсказка".|  
|[CTooltipManager::SetTooltipParams](#settooltipparams)|Настраивает внешний вид элемента управления "Всплывающая подсказка" для указанных типов элементов управления Windows.|  
|[CTooltipManager::SetTooltipText](#settooltiptext)|Задает текст и описание для элемента управления "Всплывающая подсказка".|  
|[CTooltipManager::UpdateTooltips](#updatetooltips)||  
  
## <a name="remarks"></a>Примечания  
 Используйте [класс CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, и `CTooltipManager` друг с другом, чтобы реализовать в своем приложении настроенные всплывающие подсказки. Пример использования этих классов см. в разделе [класс CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md) раздела.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtooltipmanager.h  
  
##  <a name="createtooltip"></a>CTooltipManager::CreateToolTip  
 Создает элемент управления всплывающей подсказки.  
  
```  
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,  
    CWnd* pWndParent,  
    UINT nType);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `pToolTip`  
 Ссылка на указатель всплывающей подсказки. Он задан, чтобы она указывала на только что созданный всплывающей подсказки при возврате из функции.  
  
 [in] `pWndParent`  
 Родительский объект всплывающей подсказки.  
  
 [in] `nType`  
 Тип подсказки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если всплывающая подсказка будет создана успешно.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [CTooltipManager::DeleteToolTip](#deletetooltip) удалить элемент управления tooltip, которое передается обратно в `pToolTip`.  
  
 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) тип, который задает параметры визуального отображения каждой всплывающей подсказки, он создает в зависимости от подсказка `nType` указывает. Чтобы изменить параметры для одного или нескольких типов всплывающей подсказки, вызовите [CTooltipManager::SetTooltipParams](#settooltipparams).  
  
 Типы допустимых всплывающей подсказки, перечислены в следующей таблице:  
  
|ToolTip-тип|Категория элемента управления|Пример типов|  
|------------------|----------------------|-------------------|  
|AFX_TOOLTIP_TYPE_BUTTON|Кнопка.|CMFCButton|  
|AFX_TOOLTIP_TYPE_CAPTIONBAR|Заголовок окна.|CMFCCaptionBar|  
|AFX_TOOLTIP_TYPE_DEFAULT|Любой элемент управления, который не умещается в другую категорию.|Отсутствует.|  
|AFX_TOOLTIP_TYPE_DOCKBAR|Закрепляемая область.|CDockablePane|  
|AFX_TOOLTIP_TYPE_EDIT|Текстовое поле.|Отсутствует.|  
|AFX_TOOLTIP_TYPE_MINIFRAME|Плавающего.|CPaneFrameWnd|  
|AFX_TOOLTIP_TYPE_PLANNER|Планировщик.|Отсутствует.|  
|AFX_TOOLTIP_TYPE_RIBBON|Панель ленты.|CMFCRibbonBar CMFCRibbonPanelMenuBar|  
|AFX_TOOLTIP_TYPE_TAB|Элемент управления вкладки.|CMFCTabCtrl|  
|AFX_TOOLTIP_TYPE_TOOLBAR|Панель инструментов.|CMFCToolBar CMFCPopupMenuBar|  
|AFX_TOOLTIP_TYPE_TOOLBOX|Панель элементов.|Отсутствует.|  
  
##  <a name="deletetooltip"></a>CTooltipManager::DeleteToolTip  
 Удаляет элемент управления "Всплывающая подсказка".  
  
```  
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `pToolTip`  
 Ссылка на указатель на всплывающей подсказки будут уничтожены.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для каждого [класса CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) , созданное посредством [CTooltipManager::CreateToolTip](#createtooltip). Родительский элемент управления должен вызывать этот метод из его `OnDestroy` обработчика. Это необходимо для правильного удаления подсказки от платформы. Этот метод устанавливает `pToolTip` для `NULL` перед возвратом.  
  
##  <a name="settooltipparams"></a>CTooltipManager::SetTooltipParams  
 Настраивает внешний вид элемента управления всплывающей подсказки для указанных типов элементов управления Windows.  
  
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
 Этот метод задает класс среды выполнения и начальных параметров, [CToolTipManager](../../mfc/reference/ctooltipmanager-class.md) использует при создании всплывающих подсказок. Если элемент управления вызывает [CTooltipManager::CreateToolTip](#createtooltip) и передает во всплывающей подсказке, то есть типов один из типов, обозначенном `nTypes`, диспетчера всплывающих подсказок создается элемент управления всплывающей подсказки, который является экземпляром указанного класса среды выполнения по `pRTC` и передает параметры, определенные `pParams` для создаваемой подсказки.  
  
 При вызове этого метода, все существующие владельцы подсказки сообщение AFX_WM_UPDATETOOLTIPS и их необходимо повторно создать их всплывающих подсказок с помощью [CTooltipManager::CreateToolTip](#createtooltip).  
  
 `nTypes`может быть любое сочетание допустимых подсказки типов, [CTooltipManager::CreateToolTip](#createtooltip) использует или он может быть AFX_TOOLTIP_TYPE_ALL. Если передать AFX_TOOLTIP_TYPE_ALL затрагиваются все типы всплывающей подсказки.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `SetTooltipParams` метод `CTooltipManager` класса. Этот фрагмент кода входит в состав [примера Draw Client](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#11](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]  
  
##  <a name="settooltiptext"></a>CTooltipManager::SetTooltipText  
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
 Указатель на элемент управления tooltip, для которого требуется задать текст и описание.  
  
 [in] `nType`  
 Указывает тип элемента управления, с которым связан этот всплывающей подсказки.  
  
 [in] `strText`  
 Текст, который назначен текст всплывающей подсказки.  
  
 [in] `lpszDescr`  
 Указатель на описание элемента tooltip. Может быть `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Значение `nType` должно быть то же значение, что `nType` параметр [CTooltipManager::CreateToolTip](#createtooltip) при создании всплывающей подсказки.  
  
##  <a name="updatetooltips"></a>CTooltipManager::UpdateTooltips  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void UpdateTooltips();
```  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)   
 [Класс CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)
