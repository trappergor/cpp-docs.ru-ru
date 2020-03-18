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
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425961"
---
# <a name="cdialogbar-class"></a>Класс CDialogBar

Предоставляет функциональные возможности немодального диалогового окна Windows на панели элементов управления.

## <a name="syntax"></a>Синтаксис

```
class CDialogBar : public CControlBar
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[CDialogBar:: CDialogBar](#cdialogbar)|Формирует объект `CDialogBar`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[CDialogBar:: Create](#create)|Создает диалоговую панель Windows и прикрепляет ее к объекту `CDialogBar`.|

## <a name="remarks"></a>Remarks

Диалоговая панель напоминает диалоговое окно, в котором он содержит стандартные элементы управления Windows, которые пользователь может выполнять на вкладке. Еще одним сходством является создание шаблона диалогового окна для представления диалоговой панели.

Создание и использование диалогового окна аналогично созданию и использованию объекта `CFormView`. Во-первых, используйте [Редактор диалоговых окон](../../windows/dialog-editor.md) , чтобы определить шаблон диалогового окна с WS_CHILD стиля и без другого стиля. Шаблон не должен иметь WS_VISIBLE стиля. В коде приложения вызовите конструктор для создания объекта `CDialogBar`, затем вызовите `Create`, чтобы создать окно диалогового окна и присоединить его к объекту `CDialogBar`.

Дополнительные сведения о `CDialogBar`см. в разделе панели [диалоговых](../../mfc/dialog-bars.md) окон и в [техническом примечании 31](../../mfc/tn031-control-bars.md), панели управления.

> [!NOTE]
>  В текущем выпуске объект `CDialogBar` не может содержать элементы управления Windows Forms. Дополнительные сведения об элементах управления Windows Forms в C++визуальном элементе см. в разделе [Использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CDialogBar`

## <a name="requirements"></a>Требования

**Заголовок:** афксекст. h

##  <a name="cdialogbar"></a>CDialogBar:: CDialogBar

Формирует объект `CDialogBar`.

```
CDialogBar();
```

##  <a name="create"></a>CDialogBar:: Create

Загружает шаблон ресурсов диалогового окна, заданный `lpszTemplateName` или `nIDTemplate`, создает окно диалогового окна, устанавливает его стиль и связывает с объектом `CDialogBar`.

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

*ппарентвнд*<br/>
Указатель на родительский объект `CWnd`.

*лпсзтемплатенаме*<br/>
Указатель на имя шаблона ресурса диалогового окна `CDialogBar` объекта.

*нстиле*<br/>
Стиль панели инструментов. Поддерживаются следующие дополнительные стили панелей инструментов:

- Панель управления CBRS_TOP находится в верхней части окна фрейма.

- Панель управления CBRS_BOTTOM находится в нижней части окна фрейма.

- CBRS_NOALIGN панель управления не перемещается при изменении размера родительского элемента.

- В панели управления CBRS_TOOLTIPS отображаются подсказки.

- Панель управления CBRS_SIZE_DYNAMIC является динамической.

- Панель управления CBRS_SIZE_FIXED фиксирована.

- CBRS_FLOATING панель управления является плавающей.

- Строка состояния CBRS_FLYBY отображает сведения о кнопке.

- Панель управления CBRS_HIDE_INPLACE не отображается для пользователя.

*nID*<br/>
Идентификатор элемента управления диалоговой панели.

*нидтемплате*<br/>
Идентификатор ресурса шаблона диалогового окна `CDialogBar` объекта.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Если задать стиль выравнивания CBRS_TOP или CBRS_BOTTOM, то ширина диалогового окна будет равна ширине окна фрейма и его высотой, то есть ресурса, заданного параметром *нидтемплате*. Если задать стиль выравнивания CBRS_LEFT или CBRS_RIGHT, то высота диалогового окна будет равна, так как окно фрейма и его ширина — это ресурс, заданный параметром *нидтемплате*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]

## <a name="see-also"></a>См. также раздел

[Пример CTRLBARS в MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CControlBar](../../mfc/reference/ccontrolbar-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFormView](../../mfc/reference/cformview-class.md)<br/>
[Класс CControlBar](../../mfc/reference/ccontrolbar-class.md)
