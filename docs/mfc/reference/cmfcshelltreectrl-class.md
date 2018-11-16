---
title: Класс CMFCShellTreeCtrl
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
ms.openlocfilehash: cf7e5f9c9b44524491737b27098bc91bb472cb32
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694289"
---
# <a name="cmfcshelltreectrl-class"></a>Класс CMFCShellTreeCtrl

`CMFCShellTreeCtrl` Класс расширяет [класс CTreeCtrl](../../mfc/reference/ctreectrl-class.md) функциональные возможности, отображая иерархию элементов оболочки.

Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.
## <a name="syntax"></a>Синтаксис

```
class CMFCShellTreeCtrl : public CTreeCtrl
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CMFCShellTreeCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Включает или отключает контекстное меню.|
|[CMFCShellTreeCtrl::GetFlags](#getflags)|Возвращает сочетание флагов, которые передаются [IShellFolder::EnumObjects](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects).|
|[CMFCShellTreeCtrl::GetItemPath](#getitempath)|Извлекает путь к элементу.|
|[CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist)|Возвращает указатель на [класс CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объект, который используется вместе с это `CMFCShellTreeCtrl` объект для создания окна проводника.|
|[CMFCShellTreeCtrl::OnChildNotify](#onchildnotify)|Эта функция-член вызывается родительского окна в том случае, когда он получает сообщение уведомления, которое подходит к этому окну. (Переопределяет [CWnd::OnChildNotify](../../mfc/reference/cwnd-class.md#onchildnotify).)|
|[CMFCShellTreeCtrl::OnGetItemIcon](#ongetitemicon)||
|[CMFCShellTreeCtrl::OnGetItemText](#ongetitemtext)||
|[CMFCShellTreeCtrl::Refresh](#refresh)|Обновляет и обновляет текущий `CMFCShellTreeCtrl` объекта.|
|[CMFCShellTreeCtrl::SelectPath](#selectpath)|Выбирает элемент управления соответствующего дерева, на основании предоставленного PIDL или строкового пути.|
|[CMFCShellTreeCtrl::SetFlags](#setflags)|Задает флаги для фильтрации дерева контекста (аналогичную флаги, используемые `IShellFolder::EnumObjects`).|
|[CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist)|Задает отношение между текущим `CMFCShellTreeCtrl` объекта и `CMFCShellListCtrl` объекта.|

## <a name="remarks"></a>Примечания

Этот класс расширяет `CTreeCtrl` класс, включив программы для включения в дереве элементов оболочки Windows. Этот класс может быть связано с `CMFCShellListCtrl` объекта, чтобы создать полный окно обозревателя. Затем выбрав элемент в дереве будет отображен список элементов оболочки Windows в связанном списке.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CTreeCtrl](../../mfc/reference/ctreectrl-class.md)

`CMFCShellTreeCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxshelltreeCtrl.h

## <a name="example"></a>Пример

В следующем примере показывается, как создать объект класса `CMFCShellTreeCtrl`. Этот фрагмент кода является частью [пример Explorer](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]

##  <a name="enableshellcontextmenu"></a>  CMFCShellTreeCtrl::EnableShellContextMenu

Позволяет в контекстном меню.

```
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
[in] Логическое значение, указывающее, следует ли включить в контекстном меню.

##  <a name="getflags"></a>  CMFCShellTreeCtrl::GetFlags

Возвращает флаги, установленные для [класс CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) объекта.

```
DWORD GetFlags() const;
```

### <a name="return-value"></a>Возвращаемое значение

Задайте значение DWORD, указывающее сочетание флагов, в настоящее время.

### <a name="remarks"></a>Примечания

Флаги установлены `CMFCShellTreeCtrl` отправляются в метод [IShellFolder::EnumObjects](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects) каждый раз, когда объект обновляется. Можно изменить флаги, с помощью [CMFCShellTreeCtrl::SetFlags](#setflags) метод.

##  <a name="getitempath"></a>  CMFCShellTreeCtrl::GetItemPath

Получает путь элемента в [класс CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) объекта.

```
BOOL GetItemPath(
    CString& strPath,
    HTREEITEM htreeItem = NULL) const;
```

### <a name="parameters"></a>Параметры

*strPath*<br/>
[out] Ссылка на строковый параметр. Метод записывает путь элемента для данного параметра.

*htreeItem*<br/>
[in] Метод возвращает путь для элемента управления дерева.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если выполнение прошло успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Если этот метод завершается ошибкой, *strPath* содержит пустую строку.

Если вы не укажете *hTreeItem*, этот метод пытается получить строки для текущего выбранного элемента. Если элемент не выбран и *hTreeItem* имеет значение NULL, этот метод завершается ошибкой.

##  <a name="getrelatedlist"></a>  CMFCShellTreeCtrl::GetRelatedList

Возвращает указатель на [класс CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объект, связанный с данным [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) объекта.

```
CMFCShellListCtrl* GetRelatedList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CMFCShellListCtrl` объект, связанный с данным объектом дерева элемента управления.

### <a name="remarks"></a>Примечания

С помощью `CMFCShellListCtrl` объекта вместе с `CMFCShellTreeCtrl` объекта, можно создать окно проводника. Используйте метод [CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist) для связи двух классов. После они связаны, платформа автоматически обновляет `CMFCShellListCtrl` Если элементом, выбранным в `CMFCShellTreeCtrl` изменения.

##  <a name="onchildnotify"></a>  CMFCShellTreeCtrl::OnChildNotify

```
virtual BOOL OnChildNotify(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* pLResult);
```

### <a name="parameters"></a>Параметры

[in] *сообщения*<br/>
[in] *wParam*<br/>
[in] *lParam*<br/>
[in] *pLResult*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="ongetitemicon"></a>  CMFCShellTreeCtrl::OnGetItemIcon

```
virtual int OnGetItemIcon(
    LPAFX_SHELLITEMINFO pItem,
    BOOL bSelected);
```

### <a name="parameters"></a>Параметры

[in] *pItem*<br/>
[in] *bSelected*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="ongetitemtext"></a>  CMFCShellTreeCtrl::OnGetItemText

```
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Параметры

[in] *pItem*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="refresh"></a>  CMFCShellTreeCtrl::Refresh

Обновляет и обновляет [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md).

```
void Refresh();
```

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы обновить иерархию элементов, отображаемых в `CMFCShellTreeCtrl`.

##  <a name="selectpath"></a>  CMFCShellTreeCtrl::SelectPath

Выбирает элемент в [класс CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) на основе предоставленного пути.

```
BOOL SelectPath(LPCTSTR lpszPath);
BOOL SelectPath(LPCITEMIDLIST lpidl);
```

### <a name="parameters"></a>Параметры

*lpszPath*<br/>
[in] Строка, указывающая путь к элементу.

*lpidl*<br/>
[in] PIDL, которое указывает элемент

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; В противном случае — значение E_FAIL.

##  <a name="setflags"></a>  CMFCShellTreeCtrl::SetFlags

Задает флаги для дерева контекст фильтра.

```
void SetFlags(
    DWORD dwFlags,
    BOOL bRefresh = TRUE);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
[in] Флаги для установки.

*bRefresh*<br/>
[in] Логическое значение, указывающее ли `CMFCShellTreeCtrl` должен быть обновлен немедленно.

### <a name="remarks"></a>Примечания

`CMFCShellTreeCtrl` Передает все значение флагов [IShellFolder::EnumObjects](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects). Дополнительные сведения о значениях различных флагов см. в разделе [IShellFolder::EnumObjects](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects).

##  <a name="setrelatedlist"></a>  CMFCShellTreeCtrl::SetRelatedList

Связывает [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) со [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) объекта.

```
void SetRelatedList(CMFCShellListCtrl* pShellList);
```

### <a name="parameters"></a>Параметры

*pShellList*<br/>
[in] Указатель на `CMFCShellListCtrl` объект.

### <a name="remarks"></a>Примечания

Этот метод связывает `CMFCShellListCtrl` с `CMFCShellTreeCtrl`. Эти объекты могут отображаться в виде окна проводника: Если пользователь выбирает объект в `CMFCShellTreeCtrl`, связанные элементы в `CMFCShellListCtrl` будут обновляться автоматически.

Используйте метод [CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist) извлекаемого `CMFCShellListCtrl` связанные с `CMFCShellTreeCtrl`.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CTreeCtrl](../../mfc/reference/ctreectrl-class.md)<br/>
[Класс CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)
