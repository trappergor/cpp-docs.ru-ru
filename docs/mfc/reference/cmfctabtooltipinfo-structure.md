---
title: Структура CMFCTabToolTipInfo | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCTabToolTipInfo
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21e612615110370922d71e1acaebcda56b2e692e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435458"
---
# <a name="cmfctabtooltipinfo-structure"></a>Структура CMFCTabToolTipInfo

Эта структура предоставляет сведения о вкладке MDI, пользователь перемещается указатель.

## <a name="syntax"></a>Синтаксис

```
struct CMFCTabToolTipInfo
```

## <a name="members"></a>Участники

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|[CMFCTabToolTipInfo::m_nTabIndex](#m_ntabindex)|Указывает индекс элемента управления вкладки.|
|[CMFCTabToolTipInfo::m_pTabWnd](#m_ptabwnd)|Указатель на элемент управления вкладки.|
|[CMFCTabToolTipInfo::m_strText](#m_strtext)|Текст подсказки.|

## <a name="remarks"></a>Примечания

Указатель на `CMFCTabToolTipInfo` структуры передается как параметр AFX_WM_ON_GET_TAB_TOOLTIP сообщения. Это сообщение появляется в том случае, если включены вкладок MDI и наведении указателя мыши на элемент управления вкладками.

## <a name="example"></a>Пример

В следующем примере показан как `CMFCTabToolTipInfo` используется в [примере MDITabsDemo: MFC с вкладками MDI-приложения](../../visual-cpp-samples.md).

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

В следующем примере показан как `m_nTabIndex` используется в [примере MDITabsDemo: MFC с вкладками MDI-приложения](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

##  <a name="m_ptabwnd"></a>  CMFCTabToolTipInfo::m_pTabWnd

Указатель на элемент управления вкладки.

```
CMFCBaseTabCtrl* m_pTabWnd;
```

### <a name="example"></a>Пример

В следующем примере показан как `m_pTabWnd` используется в [примере MDITabsDemo: MFC с вкладками MDI-приложения](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

##  <a name="m_strtext"></a>  CMFCTabToolTipInfo::m_strText

Текст подсказки.

```
CString m_strText;
```

### <a name="remarks"></a>Примечания

Если строка пуста, подсказка не отображается.

### <a name="example"></a>Пример

В следующем примере показан как `m_strText` используется в [примере MDITabsDemo: MFC с вкладками MDI-приложения](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
