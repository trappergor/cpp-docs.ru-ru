---
title: Класс Кдоккаблепанеадаптер
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
ms.openlocfilehash: 88c125c63f9dbfe272f5d543e996366575fc533b
ms.sourcegitcommit: bd7ddc044f9083246614b602ef6a758775313214
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68866222"
---
# <a name="cdockablepaneadapter-class"></a>Класс Кдоккаблепанеадаптер

Обеспечивает поддержку прикрепления производных панелей от `CWnd`.

## <a name="syntax"></a>Синтаксис

```
class CDockablePaneAdapter : public CDockablePane
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кдоккаблепанеадаптер:: Жетвраппедвнд](#getwrappedwnd)|Возвращает окно в оболочке.|
|[Кдоккаблепанеадаптер:: LoadState](#loadstate)|(Переопределяет [CDockablePane:: LoadState](cdockablepane-class.md#loadstate).)|
|[Кдоккаблепанеадаптер:: SaveState](#savestate)|(Переопределяет [CDockablePane:: SaveState](cdockablepane-class.md).)|
|[Кдоккаблепанеадаптер:: Сетвраппедвнд](#setwrappedwnd)||

## <a name="remarks"></a>Примечания

Как правило, платформа создает экземпляры объектов этого класса при использовании методов [CMFCBaseTabCtrl:: аддтаб](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) или [CMFCBaseTabCtrl:: инсерттаб](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) .

Если вы хотите настроить `CDockablePaneAdapter` поведение, просто создайте производный от него новый класс и задайте в качестве сведений о классе среды выполнения окно с вкладками с помощью [CMFCBaseTabCtrl:: SetDockingBarWrapperRTC](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)\
└&nbsp;[От CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CPane](../../mfc/reference/cpane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CDockablePane](../../mfc/reference/cdockablepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[Кдоккаблепанеадаптер](../../mfc/reference/cdockablepaneadapter-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксдоккаблепанеадаптер. h

##  <a name="getwrappedwnd"></a>Кдоккаблепанеадаптер:: Жетвраппедвнд

Возвращает базовое окно для адаптера закрепляемой панели.

```
virtual CWnd* GetWrappedWnd() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно с оболочкой.

### <a name="remarks"></a>Примечания

Используйте эту функцию для доступа к окну с оболочкой.

##  <a name="loadstate"></a>Кдоккаблепанеадаптер:: LoadState

Загружает состояние панели из реестра.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Параметры

*лпсзпрофиленаме*<br/>
окне Имя профиля.

*ниндекс*<br/>
окне Индекс профиля.

*uiID*<br/>
окне Идентификатор области.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="savestate"></a>Кдоккаблепанеадаптер:: SaveState

Сохраняет состояние панели в реестре.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Параметры

*лпсзпрофиленаме*<br/>
окне Имя профиля.

*ниндекс*<br/>
окне Индекс профиля (по умолчанию используется идентификатор элемента управления окна).

*uiID*<br/>
окне Идентификатор области.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="setwrappedwnd"></a>Кдоккаблепанеадаптер:: Сетвраппедвнд

Задает базовое окно для адаптера закрепляемой панели.

```
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
окне Указатель на окно для адаптера панели, для которого необходимо выполнить перенос.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)
