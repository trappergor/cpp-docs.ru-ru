---
title: Класс CTabView
ms.date: 11/04/2016
f1_keywords:
- CTabView
- AFXTABVIEW/CTabView
- AFXTABVIEW/CTabView::AddView
- AFXTABVIEW/CTabView::FindTab
- AFXTABVIEW/CTabView::GetActiveView
- AFXTABVIEW/CTabView::GetTabControl
- AFXTABVIEW/CTabView::RemoveView
- AFXTABVIEW/CTabView::SetActiveView
- AFXTABVIEW/CTabView::IsScrollBar
- AFXTABVIEW/CTabView::OnActivateView
helpviewer_keywords:
- CTabView [MFC], AddView
- CTabView [MFC], FindTab
- CTabView [MFC], GetActiveView
- CTabView [MFC], GetTabControl
- CTabView [MFC], RemoveView
- CTabView [MFC], SetActiveView
- CTabView [MFC], IsScrollBar
- CTabView [MFC], OnActivateView
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
ms.openlocfilehash: 56640edbd0d2e74a1cc00dad5441350ad3d35725
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346243"
---
# <a name="ctabview-class"></a>Класс CTabView

`CTabView` Класс упрощает использование класса элемента управления tab ( [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)) в приложениях, использующих архитектуру документа/представления MFC.

## <a name="syntax"></a>Синтаксис

```
class CTabbedView : public CView
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CTabView::AddView](#addview)|Добавляет новое представление вкладок элемента управления.|
|[CTabView::FindTab](#findtab)|Возвращает индекс указанного представления в набор вкладок.|
|[CTabView::GetActiveView](#getactiveview)|Возвращает указатель на данный момент активное представление|
|[CTabView::GetTabControl](#gettabcontrol)|Возвращает ссылку на элемент управления вкладки, связанный с представлением.|
|[CTabView::RemoveView](#removeview)|Удаляет представление из вкладок элемента управления.|
|[CTabView::SetActiveView](#setactiveview)|Делает активным представлением.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[CTabView::IsScrollBar](#isscrollbar)|Вызывается платформой при создании представления вкладки, чтобы определить, имеет ли представление вкладки Общие горизонтальную полосу прокрутки.|
|[CTabView::OnActivateView](#onactivateview)|Вызывается платформой, когда представление вкладки становится активным или неактивным.|

## <a name="remarks"></a>Примечания

Этот класс позволяет легко перевести представление со вкладками в приложении документов и представлений. `CTabView` — `CView`-производный класс, который содержит встроенный `CMFCTabCtrl` объекта. `CTabView` обрабатывает все сообщения, необходимые для поддержки `CMFCTabCtrl` объекта. Просто наследуйте класс от `CTabView` и подключить его к приложению, а затем добавьте `CView`-производные классы с помощью `AddView` метод. Элемент управления вкладки будет отображать эти представления как вкладки.

Например, возможно, документ, который может быть представлен по-разному: как электронную таблицу, диаграмму, редактируемую форму и т. д. Можно создавать отдельные представления, графические данные, при необходимости, они вставляются в `CTabView`-объект, производной от и их с вкладками без дополнительного кодирования.

[Образец TabbedView: Приложение представления с вкладками MFC](../../overview/visual-cpp-samples.md) иллюстрирует использование `CTabView`.

## <a name="example"></a>Пример

В следующем примере показан как `CTabView` приведенная в образце TabbedView.

[!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]

## <a name="requirements"></a>Требования

**Заголовок:** afxTabView.h

##  <a name="addview"></a>  CTabView::AddView

Добавляет представление вкладок элемента управления.

```
int AddView(
    CRuntimeClass* pViewClass,
    const CString& strViewLabel,
    int iIndex=-1,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>Параметры

*pViewClass*<br/>
[in] Указатель на класс среды выполнения inserted представления.

*strViewLabel*<br/>
[in] Задает текст для вкладки.

*iIndex*<br/>
[in] Указывает, отсчитываемая от нуля позиция, по которому следует вставить в представлении. Если позиция находится значение -1 в конце вставляется новая вкладка.

*pContext*<br/>
[in] Указатель на `CCreateContext` представления.

### <a name="return-value"></a>Возвращаемое значение

Индекс представления, если этот метод выполняется успешно. В противном случае — значение -1.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для добавления вкладок, которое внедрено в кадре представления.

##  <a name="findtab"></a>  CTabView::FindTab

Возвращает индекс указанного представления в набор вкладок.

```
int FindTab(HWND hWndView) const;
```

### <a name="parameters"></a>Параметры

*hWndView*<br/>
[in] Дескриптор представления.

### <a name="return-value"></a>Возвращаемое значение

Индекс представления, если он найден; в противном случае — значение -1.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для извлечения индекса представления с указанным дескриптором.

##  <a name="getactiveview"></a>  CTabView::GetActiveView

Возвращает указатель на данный момент активное представление.

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Допустимый указатель на активное представление, или значение NULL, если нет активное представление.

### <a name="remarks"></a>Примечания

##  <a name="gettabcontrol"></a>  CTabView::GetTabControl

Возвращает ссылку на элемент управления вкладки, связанный с представлением.

```
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент управления вкладки, связанный с представлением.

##  <a name="isscrollbar"></a>  CTabView::IsScrollBar

Вызывается платформой при создании представления вкладки, чтобы определить, имеет ли представление вкладки Общие горизонтальную полосу прокрутки.

```
virtual BOOL IsScrollBar() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если представление вкладки должны создаваться вместе с полосу прокрутки общего. В противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой при *CTabView* в процессе создания объекта.

Переопределить *IsScrollBar* метод в *CTabView*-производного класса и возвращает значение TRUE, если вы хотите создать представление, которое имеет общий горизонтальную полосу прокрутки.

##  <a name="onactivateview"></a>  CTabView::OnActivateView

Вызывается платформой, когда представление вкладки становится активным или неактивным.

```
virtual void OnActivateView(CView* view);
```

### <a name="parameters"></a>Параметры

*представление*<br/>
[in] Указатель на представление.

### <a name="remarks"></a>Примечания

Реализация по умолчанию не выполняет никаких действий. Переопределите этот метод в `CTabView`-производный класс для обработки этого уведомления.

##  <a name="removeview"></a>  CTabView::RemoveView

Удаляет представление из вкладок элемента управления.

```
BOOL RemoveView(int iTabNum);
```

### <a name="parameters"></a>Параметры

*iTabNum*<br/>
[in] Индекс удаляемого представления.

### <a name="return-value"></a>Возвращаемое значение

Индекс удален представления, если этот метод выполняется успешно. В противном случае-1.

### <a name="remarks"></a>Примечания

##  <a name="setactiveview"></a>  CTabView::SetActiveView

Делает активным представлением.

```
BOOL SetActiveView(int iTabNum);
```

### <a name="parameters"></a>Параметры

*iTabNum*<br/>
[in] Отсчитываемый от нуля индекс представление вкладки.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если указанное представление сделан активным, FALSE, если используется недопустимый индекс представления.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [CMFCTabCtrl::SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab).

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CMFCTabCtrl](../../mfc/reference/ctabview-class.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)
