---
title: Класс CTooltipManager
ms.date: 11/04/2016
f1_keywords:
- CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager::CreateToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::DeleteToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipParams
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipText
- AFXTOOLTIPMANAGER/CTooltipManager::UpdateTooltips
helpviewer_keywords:
- CTooltipManager [MFC], CreateToolTip
- CTooltipManager [MFC], DeleteToolTip
- CTooltipManager [MFC], SetTooltipParams
- CTooltipManager [MFC], SetTooltipText
- CTooltipManager [MFC], UpdateTooltips
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
ms.openlocfilehash: e8b88f2722f5a4379276f13c2ef159aa4d120533
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323756"
---
# <a name="ctooltipmanager-class"></a>Класс CTooltipManager

Хранит сведения среды выполнения о подсказках. Экземпляр класса `CTooltipManager` создается один раз для каждого приложения.

## <a name="syntax"></a>Синтаксис

```
class CTooltipManager : public CObject
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
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

##  <a name="createtooltip"></a>  CTooltipManager::CreateToolTip

Создает элемент управления tooltip.

```
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,
    CWnd* pWndParent,
    UINT nType);
```

### <a name="parameters"></a>Параметры

*pToolTip*<br/>
[out] Ссылка на указатель всплывающей подсказки. Он настраивается для только что созданный всплывающей подсказки при возврате функции.

*pWndParent*<br/>
[in] Родительский объект подсказки.

*nType*<br/>
[in] Тип подсказки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если всплывающая подсказка будет создан.

### <a name="remarks"></a>Примечания

Необходимо вызвать [CTooltipManager::DeleteToolTip](#deletetooltip) удалить элемент управления всплывающей подсказки, который передается обратно в *pToolTip*.

[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) тип наборы параметров визуальному представлению каждого подсказки, он создает основанные на всплывающей подсказки, который *nType* указывает. Чтобы изменить параметры для одного или нескольких типов всплывающей подсказки, вызовите [CTooltipManager::SetTooltipParams](#settooltipparams).

Типы допустимых всплывающей подсказки, перечислены в следующей таблице.

|Тип подсказки|Категория элемента управления|Пример типов|
|------------------|----------------------|-------------------|
|AFX_TOOLTIP_TYPE_BUTTON|Кнопка.|CMFCButton|
|AFX_TOOLTIP_TYPE_CAPTIONBAR|Заголовок окна.|CMFCCaptionBar|
|AFX_TOOLTIP_TYPE_DEFAULT|Любой элемент управления, который не умещается другую категорию.|Отсутствует.|
|AFX_TOOLTIP_TYPE_DOCKBAR|Закрепляемая область.|CDockablePane|
|AFX_TOOLTIP_TYPE_EDIT|Текстовое поле.|Отсутствует.|
|AFX_TOOLTIP_TYPE_MINIFRAME|Области.|CPaneFrameWnd|
|AFX_TOOLTIP_TYPE_PLANNER|Планировщик.|Отсутствует.|
|AFX_TOOLTIP_TYPE_RIBBON|Панели ленты.|CMFCRibbonBar, CMFCRibbonPanelMenuBar|
|AFX_TOOLTIP_TYPE_TAB|Набор вкладок.|CMFCTabCtrl|
|AFX_TOOLTIP_TYPE_TOOLBAR|Панель инструментов.|CMFCToolBar CMFCPopupMenuBar|
|AFX_TOOLTIP_TYPE_TOOLBOX|Панель инструментов.|Отсутствует.|

##  <a name="deletetooltip"></a>  CTooltipManager::DeleteToolTip

Удаляет элемент управления "Всплывающая подсказка".

```
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```

### <a name="parameters"></a>Параметры

*pToolTip*<br/>
[in, out] Ссылка на указатель на всплывающей подсказки будут уничтожены.

### <a name="remarks"></a>Примечания

Этот метод вызывается для каждого [класс CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) , созданный с [CTooltipManager::CreateToolTip](#createtooltip). Родительский элемент управления должны вызывать этот метод из его `OnDestroy` обработчика. Это необходимо для правильного удаления подсказки из .NET framework. Этот метод задает *pToolTip* значение NULL, перед возвращением.

##  <a name="settooltipparams"></a>  CTooltipManager::SetTooltipParams

Настраивает внешний вид элемента управления всплывающей подсказки для указанных типов элемента управления Windows.

```
void SetTooltipParams(
    UINT nTypes,
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),
    CMFCToolTipInfo* pParams=NULL);
```

### <a name="parameters"></a>Параметры

*nTypes*<br/>
[in] Указывает типы элементов управления.

*pRTC*<br/>
[in] Класс среды выполнения пользовательскую подсказку.

*pParams*<br/>
[in] Параметры всплывающей подсказки.

### <a name="remarks"></a>Примечания

Этот метод задает класс среды выполнения и начальные параметры, [CToolTipManager](../../mfc/reference/ctooltipmanager-class.md) использует при создании подсказки. Когда элемент управления вызывает [CTooltipManager::CreateToolTip](#createtooltip) и передает в подсказке типа, который является одним из типов, обозначается *nTypes*, диспетчера всплывающих подсказок создает элемент управления всплывающей подсказки, который является экземпляром класса класс среды выполнения, определяемое *pRTC* и передает параметрам, указанным *pParams* на новый элемент управления tooltip.

При вызове этого метода, все существующие владельцы подсказки сообщение AFX_WM_UPDATETOOLTIPS и их необходимо повторно создать их подсказки с помощью [CTooltipManager::CreateToolTip](#createtooltip).

*nTypes* может быть любое сочетание допустимых подсказки типы, которые [CTooltipManager::CreateToolTip](#createtooltip) использует или он может быть AFX_TOOLTIP_TYPE_ALL. Если передать AFX_TOOLTIP_TYPE_ALL, влияют на все типы всплывающей подсказки.

### <a name="example"></a>Пример

Следующий пример демонстрирует, как использовать `SetTooltipParams` метод `CTooltipManager` класса. Этот фрагмент кода входит в состав [примера Draw Client](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#11](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]

##  <a name="settooltiptext"></a>  CTooltipManager::SetTooltipText

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

*pTI*<br/>
[in] Указатель на объект TOOLINFO.

*pToolTip*<br/>
[in, out] Указатель на элемент управления tooltip, для которого требуется задать текст и описание.

*nType*<br/>
[in] Указывает тип элемента управления, с которым связан этот всплывающей подсказки.

*strText*<br/>
[in] Текст, набор в виде текста всплывающей подсказки.

*lpszDescr*<br/>
[in] Указатель на описание элемента tooltip. Может иметь значение NULL.

### <a name="remarks"></a>Примечания

Значение *nType* должно быть то же значение, что *nType* параметр [CTooltipManager::CreateToolTip](#createtooltip) при создании всплывающей подсказки.

##  <a name="updatetooltips"></a>  CTooltipManager::UpdateTooltips

Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.

```
void UpdateTooltips();
```

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)<br/>
[Класс CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)
