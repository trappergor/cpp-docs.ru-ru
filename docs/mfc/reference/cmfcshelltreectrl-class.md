---
title: Класс Кмфкшеллтриктрл
ms.date: 11/04/2016
f1_keywords:
- CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::EnableShellContextMenu
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetItemPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetRelatedList
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnChildNotify
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemIcon
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemText
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::Refresh
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SelectPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetRelatedList
helpviewer_keywords:
- CMFCShellTreeCtrl [MFC], EnableShellContextMenu
- CMFCShellTreeCtrl [MFC], GetFlags
- CMFCShellTreeCtrl [MFC], GetItemPath
- CMFCShellTreeCtrl [MFC], GetRelatedList
- CMFCShellTreeCtrl [MFC], OnChildNotify
- CMFCShellTreeCtrl [MFC], OnGetItemIcon
- CMFCShellTreeCtrl [MFC], OnGetItemText
- CMFCShellTreeCtrl [MFC], Refresh
- CMFCShellTreeCtrl [MFC], SelectPath
- CMFCShellTreeCtrl [MFC], SetFlags
- CMFCShellTreeCtrl [MFC], SetRelatedList
ms.assetid: 3d1da715-9554-4ed7-968c-055c48146267
ms.openlocfilehash: 97136342049a54d45af893962025f01eda4366d4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504908"
---
# <a name="cmfcshelltreectrl-class"></a>Класс Кмфкшеллтриктрл

Класс расширяет функциональные возможности [класса CTreeCtrl](../../mfc/reference/ctreectrl-class.md) , отображая иерархию элементов оболочки. `CMFCShellTreeCtrl`

Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.
## <a name="syntax"></a>Синтаксис

```
class CMFCShellTreeCtrl : public CTreeCtrl
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кмфкшеллтриктрл:: Енаблешеллконтекстмену](#enableshellcontextmenu)|Включает или отключает контекстное меню.|
|[Флаги Кмфкшеллтриктрл:: "](#getflags)|Возвращает сочетание флагов, которые передаются в [ишеллфолдер:: енумобжектс](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects).|
|[Кмфкшеллтриктрл:: Жетитемпас](#getitempath)|Извлекает путь к элементу.|
|[Кмфкшеллтриктрл:: Жетрелатедлист](#getrelatedlist)|Возвращает указатель на объект [класса кмфкшелллистктрл](../../mfc/reference/cmfcshelllistctrl-class.md) , используемый вместе с этим `CMFCShellTreeCtrl` объектом для создания окна, похожего на обозреватель.|
|[CMFCShellTreeCtrl::OnChildNotify](#onchildnotify)|Эта функция-член вызывается родительским окном этого окна при получении сообщения уведомления, которое применяется к этому окну. (Переопределяет [CWnd:: ончилднотифи](../../mfc/reference/cwnd-class.md#onchildnotify).)|
|[CMFCShellTreeCtrl::OnGetItemIcon](#ongetitemicon)||
|[CMFCShellTreeCtrl::OnGetItemText](#ongetitemtext)||
|[Кмфкшеллтриктрл:: Refresh](#refresh)|Обновляет и перерисовывает текущий `CMFCShellTreeCtrl` объект.|
|[Кмфкшеллтриктрл:: Селектпас](#selectpath)|Выбирает соответствующий элемент управления "дерево" на основе заданного ПИДЛ или пути к строке.|
|[Кмфкшеллтриктрл:: Сетфлагс](#setflags)|Устанавливает флаги для фильтрации контекста дерева (аналогично флагам, `IShellFolder::EnumObjects`используемым).|
|[Кмфкшеллтриктрл:: Сетрелатедлист](#setrelatedlist)|Задает отношение между текущим `CMFCShellTreeCtrl` объектом `CMFCShellListCtrl` и объектом.|

## <a name="remarks"></a>Примечания

Этот класс расширяет `CTreeCtrl` класс, позволяя программе включать в дерево элементы оболочки Windows. Этот класс может быть связан с `CMFCShellListCtrl` объектом для создания полного окна проводника. Затем при выборе элемента в дереве отображается список элементов оболочки Windows в связанном списке.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CTreeCtrl](../../mfc/reference/ctreectrl-class.md)

`CMFCShellTreeCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** афксшеллтриктрл. h

## <a name="example"></a>Пример

В следующем примере показывается, как создать объект класса `CMFCShellTreeCtrl`. Этот фрагмент кода является частью [примера обозревателя](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]

##  <a name="enableshellcontextmenu"></a>Кмфкшеллтриктрл:: Енаблешеллконтекстмену

Включает контекстное меню.

```
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
окне Логическое значение, указывающее, следует ли включить контекстное меню.

##  <a name="getflags"></a>Флаги Кмфкшеллтриктрл:: "

Возвращает флаги, заданные для объекта [класса кмфкшеллтриктрл](../../mfc/reference/cmfcshelltreectrl-class.md) .

```
DWORD GetFlags() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение типа DWORD, указывающее сочетание флагов, заданных в данный момент.

### <a name="remarks"></a>Примечания

Флаги, заданные `CMFCShellTreeCtrl` в, отправляются в метод [ишеллфолдер:: енумобжектс](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects) при каждом обновлении объекта. Флаги можно изменить с помощью метода [кмфкшеллтриктрл:: сетфлагс](#setflags) .

##  <a name="getitempath"></a>Кмфкшеллтриктрл:: Жетитемпас

Извлекает путь к элементу в объекте [класса кмфкшеллтриктрл](../../mfc/reference/cmfcshelltreectrl-class.md) .

```
BOOL GetItemPath(
    CString& strPath,
    HTREEITEM htreeItem = NULL) const;
```

### <a name="parameters"></a>Параметры

*strPath*<br/>
заполняет Ссылка на строковый параметр. Метод записывает путь к элементу в этот параметр.

*хтриитем*<br/>
окне Метод получает путь для этого элемента управления "дерево".

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успешного выполнения. В противном случае — 0.

### <a name="remarks"></a>Примечания

Если этот метод завершается с ошибкой, *strPath* содержит пустую строку.

Если не указать *хтриитем*, этот метод попытается получить строку для выбранного в данный момент элемента. Если элемент не выбран и *хтриитем* имеет значение null, этот метод завершается ошибкой.

##  <a name="getrelatedlist"></a>Кмфкшеллтриктрл:: Жетрелатедлист

Возвращает указатель на объект [класса кмфкшелллистктрл](../../mfc/reference/cmfcshelllistctrl-class.md) , связанный с этим объектом [кмфкшеллтриктрл](../../mfc/reference/cmfcshelltreectrl-class.md) .

```
CMFCShellListCtrl* GetRelatedList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CMFCShellListCtrl` объект, связанный с данным объектом управления "дерево".

### <a name="remarks"></a>Примечания

Используя `CMFCShellListCtrl` объект вместе `CMFCShellTreeCtrl` с объектом, можно создать окно, похожее на обозреватель. Чтобы связать эти два класса, используйте метод [кмфкшеллтриктрл:: сетрелатедлист](#setrelatedlist) . После того как они связаны, платформа автоматически обновляет значение `CMFCShellListCtrl` , если выбор `CMFCShellTreeCtrl` изменяется.

##  <a name="onchildnotify"></a>  CMFCShellTreeCtrl::OnChildNotify

```
virtual BOOL OnChildNotify(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* pLResult);
```

### <a name="parameters"></a>Параметры

окне *сообщение об ошибке*<br/>
окне *wParam*<br/>
окне *lParam*<br/>
окне *плресулт*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="ongetitemicon"></a>  CMFCShellTreeCtrl::OnGetItemIcon

```
virtual int OnGetItemIcon(
    LPAFX_SHELLITEMINFO pItem,
    BOOL bSelected);
```

### <a name="parameters"></a>Параметры

окне *питем*<br/>
окне *бселектед*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="ongetitemtext"></a>  CMFCShellTreeCtrl::OnGetItemText

```
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Параметры

окне *питем*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="refresh"></a>Кмфкшеллтриктрл:: Refresh

Обновляет и перерисовывает [кмфкшеллтриктрл](../../mfc/reference/cmfcshelltreectrl-class.md).

```
void Refresh();
```

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы обновить иерархию элементов, `CMFCShellTreeCtrl`отображаемых в.

##  <a name="selectpath"></a>Кмфкшеллтриктрл:: Селектпас

Выбирает элемент в [классе кмфкшеллтриктрл](../../mfc/reference/cmfcshelltreectrl-class.md) на основе заданного пути.

```
BOOL SelectPath(LPCTSTR lpszPath);
BOOL SelectPath(LPCITEMIDLIST lpidl);
```

### <a name="parameters"></a>Параметры

*лпсзпас*<br/>
окне Строка, указывающая путь к элементу.

*лпидл*<br/>
окне Объект ПИДЛ, указывающий элемент

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK в случае успешного выполнения; E_FAIL в противном случае.

##  <a name="setflags"></a>Кмфкшеллтриктрл:: Сетфлагс

Устанавливает флаги для фильтрации контекста дерева.

```
void SetFlags(
    DWORD dwFlags,
    BOOL bRefresh = TRUE);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
окне Устанавливаемые флаги.

*брефреш*<br/>
окне Логическое значение, указывающее, `CMFCShellTreeCtrl` следует ли обновлять немедленно.

### <a name="remarks"></a>Примечания

Все флаги `CMFCShellTreeCtrl` передаются в [IShellFolder::EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects). Дополнительные сведения о значениях различных флагов см. в разделе [ишеллфолдер:: енумобжектс](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects).

##  <a name="setrelatedlist"></a>Кмфкшеллтриктрл:: Сетрелатедлист

Связывает объект [кмфкшелллистктрл](../../mfc/reference/cmfcshelllistctrl-class.md) с объектом [кмфкшеллтриктрл](../../mfc/reference/cmfcshelltreectrl-class.md) .

```
void SetRelatedList(CMFCShellListCtrl* pShellList);
```

### <a name="parameters"></a>Параметры

*пшелллист*<br/>
окне Указатель на `CMFCShellListCtrl` объект.

### <a name="remarks"></a>Примечания

Этот метод связывает `CMFCShellListCtrl` `CMFCShellTreeCtrl`с. Эти объекты могут отображаться как окно `CMFCShellTreeCtrl`, похожее на обозреватель: Если пользователь выбирает объект в, связанные элементы `CMFCShellListCtrl` в будут автоматически обновлены.

Используйте метод [кмфкшеллтриктрл:: жетрелатедлист](#getrelatedlist) , чтобы получить объект `CMFCShellListCtrl` , связанный с `CMFCShellTreeCtrl`.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CTreeCtrl](../../mfc/reference/ctreectrl-class.md)<br/>
[Класс CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)
