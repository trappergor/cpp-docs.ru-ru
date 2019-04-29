---
title: Класс CDockablePaneAdapter
ms.date: 11/04/2016
f1_keywords:
- CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::GetWrappedWnd
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::LoadState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SaveState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SetWrappedWnd
helpviewer_keywords:
- CDockablePaneAdapter [MFC], GetWrappedWnd
- CDockablePaneAdapter [MFC], LoadState
- CDockablePaneAdapter [MFC], SaveState
- CDockablePaneAdapter [MFC], SetWrappedWnd
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
ms.openlocfilehash: 8f184bab564b4867138608b735c67b328e1a21cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391248"
---
# <a name="cdockablepaneadapter-class"></a>Класс CDockablePaneAdapter

Обеспечивает поддержку прикрепления производных панелей от `CWnd`.

## <a name="syntax"></a>Синтаксис

```
class CDockablePaneAdapter : public CDockablePane
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CDockablePaneAdapter::GetWrappedWnd](#getwrappedwnd)|Возвращает окно в оболочке.|
|[CDockablePaneAdapter::LoadState](#loadstate)|(Переопределяет [CDockablePane::LoadState](cdockablepane-class.md#loadstate).)|
|[CDockablePaneAdapter::SaveState](#savestate)|(Переопределяет [CDockablePane::SaveState](cdockablepane-class.md).)|
|[CDockablePaneAdapter::SetWrappedWnd](#setwrappedwnd)||

## <a name="remarks"></a>Примечания

Как правило, платформа создает экземпляры объектов этого класса при использовании [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) или [CMFCBaseTabCtrl::InsertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) методы.

Если вы хотите настроить `CDockablePaneAdapter` поведение, просто создать новый класс, производный от него и задать сведения о классе среды выполнения в окно с вкладками с помощью [CMFCBaseTabCtrl::SetDockingBarWrapperRTC](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxDockablePaneAdapter.h

##  <a name="getwrappedwnd"></a>  CDockablePaneAdapter::GetWrappedWnd

Возвращает окна для адаптера закрепляемую панель.

```
virtual CWnd* GetWrappedWnd() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно в оболочке.

### <a name="remarks"></a>Примечания

Эту функцию можно используйте для доступа к окно в оболочке.

##  <a name="loadstate"></a>  CDockablePaneAdapter::LoadState

Загружает состояние панели из реестра.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
[in] Имя профиля.

*nIndex*<br/>
[in] Индекс профиля.

*uiID*<br/>
[in] Идентификатор области.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="savestate"></a>  CDockablePaneAdapter::SaveState

Сохраняет состояние панели в реестр.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
[in] Имя профиля.

*nIndex*<br/>
[in] Индекс профиля (по умолчанию — идентификатор элемента управления окна).

*uiID*<br/>
[in] Идентификатор области.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="setwrappedwnd"></a>  CDockablePaneAdapter::SetWrappedWnd

Задает нижележащего окна для адаптера закрепляемую панель.

```
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
[in] Указатель на окно для адаптера области программы-оболочки.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)
