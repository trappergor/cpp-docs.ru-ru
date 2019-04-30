---
title: Класс CDialogBar
ms.date: 11/04/2016
f1_keywords:
- CDialogBar
- AFXEXT/CDialogBar
- AFXEXT/CDialogBar::CDialogBar
- AFXEXT/CDialogBar::Create
helpviewer_keywords:
- CDialogBar [MFC], CDialogBar
- CDialogBar [MFC], Create
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
ms.openlocfilehash: af84c5239a9cb3cbddb1ab4f0230e5b1a3373573
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400725"
---
# <a name="cdialogbar-class"></a>Класс CDialogBar

Предоставляет функциональные возможности немодального диалогового окна Windows на панели элементов управления.

## <a name="syntax"></a>Синтаксис

```
class CDialogBar : public CControlBar
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CDialogBar::CDialogBar](#cdialogbar)|Создает объект `CDialogBar`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CDialogBar::Create](#create)|Создает панель диалогового окна Windows и присоединяет его к `CDialogBar` объекта.|

## <a name="remarks"></a>Примечания

Диалоговая панель напоминает диалоговое окно, в том, что он содержит стандартные элементы управления Windows, которые пользователь может перейти между. Другой аспект имеет создать шаблон диалогового окна для диалоговой панели представления.

Создание и использование диалоговой панели аналогичен созданию и использованию `CFormView` объекта. Во-первых, используйте [редактор диалоговых окон](../../windows/dialog-editor.md) определить шаблон диалогового окна со стилем WS_CHILD и других стиль не задан. Шаблон не должен иметь WS_VISIBLE стиль. В коде приложения вызовите конструктор для создания `CDialogBar` объекта, а затем вызовите `Create` для создания окна диалоговой панели и присоединить его к `CDialogBar` объекта.

Дополнительные сведения о `CDialogBar`, см. в статье [диалоговые панели](../../mfc/dialog-bars.md) и [Технические примечания 31](../../mfc/tn031-control-bars.md), панелями элементов управления.

> [!NOTE]
>  В текущем выпуске `CDialogBar` не может размещать элементы управления Windows Forms. Дополнительные сведения об элементах управления Windows Forms в Visual C++ см. в разделе [использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CDialogBar`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

##  <a name="cdialogbar"></a>  CDialogBar::CDialogBar

Создает объект `CDialogBar`.

```
CDialogBar();
```

##  <a name="create"></a>  CDialogBar::Create

Загружает шаблон диалогового окна ресурсов, указанный `lpszTemplateName` или `nIDTemplate`, создает окно диалоговая панель, задает его стиль и связывает его с `CDialogBar` объекта.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID);

virtual BOOL Create(
    CWnd* pParentWnd,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на родительский `CWnd` объекта.

*lpszTemplateName*<br/>
Указатель на имя `CDialogBar` объекта диалоговых ресурсов шаблона.

*nStyle*<br/>
Стиль панели инструментов. Существуют следующие стили дополнительных инструментов, которые поддерживаются:

- Панель элементов управления CBRS_TOP — в верхней части фрейма окна.

- Панель элементов управления CBRS_BOTTOM — в нижней части окна фрейма.

- При изменении размера родительской панели элементов управления CBRS_NOALIGN не перемещен.

- Панель элементов управления CBRS_TOOLTIPS отображает всплывающие подсказки.

- Панель элементов управления CBRS_SIZE_DYNAMIC является динамическим.

- Панель элементов управления CBRS_SIZE_FIXED является фиксированным.

- Панель элементов управления CBRS_FLOATING с плавающей запятой.

- Строка состояния CBRS_FLYBY отображает сведения о кнопке.

- Панель элементов управления CBRS_HIDE_INPLACE не отображается для пользователя.

*nID*<br/>
Идентификатор элемента управления панели диалогового окна.

*nIDTemplate*<br/>
Идентификатор ресурса `CDialogBar` шаблона диалогового окна объекта.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Если указать CBRS_TOP или CBRS_BOTTOM стиль, ширина панели диалогового окна является то, что окна фрейма и высоту, — это ресурс, заданный параметром *nIDTemplate*. Если указать CBRS_LEFT или CBRS_RIGHT стиль выравнивания, высоты панели диалогового окна является то, что окна фрейма и его ширину, — это ресурс, заданный параметром *nIDTemplate*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[Класс CControlBar](../../mfc/reference/ccontrolbar-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFormView](../../mfc/reference/cformview-class.md)<br/>
[Класс CControlBar](../../mfc/reference/ccontrolbar-class.md)
