---
title: Структура CMFCTabToolTipInfo
ms.date: 11/04/2016
f1_keywords:
- CMFCTabToolTipInfo
helpviewer_keywords:
- CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
ms.openlocfilehash: 1e10e74729a1a4bde90ca22abdcc1a75b41c95db
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260821"
---
# <a name="cmfctabtooltipinfo-structure"></a>Структура CMFCTabToolTipInfo

Эта структура предоставляет сведения о вкладке MDI, пользователь перемещается указатель.

## <a name="syntax"></a>Синтаксис

```
struct CMFCTabToolTipInfo
```

## <a name="members"></a>Участники

### <a name="data-members"></a>Элементы данных

|name|Описание:|
|----------|-----------------|
|[CMFCTabToolTipInfo::m_nTabIndex](#m_ntabindex)|Указывает индекс элемента управления вкладки.|
|[CMFCTabToolTipInfo::m_pTabWnd](#m_ptabwnd)|Указатель на элемент управления вкладки.|
|[CMFCTabToolTipInfo::m_strText](#m_strtext)|Текст подсказки.|

## <a name="remarks"></a>Примечания

Указатель на `CMFCTabToolTipInfo` структуры передается как параметр AFX_WM_ON_GET_TAB_TOOLTIP сообщения. Это сообщение появляется в том случае, если включены вкладок MDI и наведении указателя мыши на элемент управления вкладками.

## <a name="example"></a>Пример

В следующем примере показан как `CMFCTabToolTipInfo` используется в [примере MDITabsDemo: Приложение MDI с вкладками MFC](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxbasetabctrl.h

##  <a name="m_ntabindex"></a>  CMFCTabToolTipInfo::m_nTabIndex

Указывает индекс элемента управления вкладки.

```
int m_nTabIndex;
```

### <a name="remarks"></a>Примечания

Индекс вкладки, по которому пользователь перемещается.

### <a name="example"></a>Пример

В следующем примере показан как `m_nTabIndex` используется в [примере MDITabsDemo: Приложение MDI с вкладками MFC](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

##  <a name="m_ptabwnd"></a>  CMFCTabToolTipInfo::m_pTabWnd

Указатель на элемент управления вкладки.

```
CMFCBaseTabCtrl* m_pTabWnd;
```

### <a name="example"></a>Пример

В следующем примере показан как `m_pTabWnd` используется в [примере MDITabsDemo: Приложение MDI с вкладками MFC](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

##  <a name="m_strtext"></a>  CMFCTabToolTipInfo::m_strText

Текст подсказки.

```
CString m_strText;
```

### <a name="remarks"></a>Примечания

Если строка пуста, подсказка не отображается.

### <a name="example"></a>Пример

В следующем примере показан как `m_strText` используется в [примере MDITabsDemo: Приложение MDI с вкладками MFC](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
