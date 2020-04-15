---
title: Класс CWinFormsView
ms.date: 11/04/2016
f1_keywords:
- CWinFormsView
- AFXWINFORMS/CWinFormsView
- AFXWINFORMS/CWinFormsView::CWinFormsView
- AFXWINFORMS/CWinFormsView::GetControl
helpviewer_keywords:
- CWinFormsView [MFC], CWinFormsView
- CWinFormsView [MFC], GetControl
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
ms.openlocfilehash: 6eb6b9e385e9dbc96eb3b62ffb80909e54569e97
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369604"
---
# <a name="cwinformsview-class"></a>Класс CWinFormsView

Предоставляет универсальную функцию для размещения элементов управления Windows Forms в качестве представления MFC.

## <a name="syntax"></a>Синтаксис

```
class CWinFormsView : public CView;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CWinFormsView::CWinFormsView](#cwinformsview)|Формирует объект `CWinFormsView`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWinFormsView::GetControl](#getcontrol)|Извлекает указатель на элемент управления форм Windows.|

### <a name="public-operators"></a>Открытые операторы

|Имя||
|----------|-|
|[CWinFormsView::Управление оператором](#operator_control)|Отбрасывает тип в качестве указателя на элемент управления формами Windows.|

## <a name="remarks"></a>Remarks

MFC использует `CWinFormsView` класс для размещения управления системами Windows .NET Framework В представлении MFC. Контроль является ребенком родного вида и занимает всю клиентскую область зрения MFC. Результат аналогичен `CFormView` представлению, что позволяет воспользоваться преимуществами дизайнера Форм Windows и запустить время для создания богатых представлений на основе форм.

Для получения дополнительной информации об использовании форм Windows, [см.](../../dotnet/using-a-windows-form-user-control-in-mfc.md)

> [!NOTE]
> Интеграция MFC Windows Forms работает только в проектах, которые динамически связывают сяпонического отношения с MFC (проекты, в которых определяется AFXDLL).

> [!NOTE]
> CWinFormsView не поддерживает окно сплиттера MFC [(класс CSplitterWnd).](../../mfc/reference/csplitterwnd-class.md) В настоящее время поддерживается только управление Сплиттером форм Windows.

## <a name="requirements"></a>Требования

**Заголовок:** afxwinforms.h

## <a name="cwinformsviewcwinformsview"></a><a name="cwinformsview"></a>CWinFormsView::CWinFormsView

Формирует объект `CWinFormsView`.

```
CWinFormsView(System::Type^ pManagedViewType);
```

### <a name="parameters"></a>Параметры

*pManagedViewType*<br/>
Указатель на тип данных пользовательского управления Windows Forms.

### <a name="example"></a>Пример

В следующем примере `CUserView` класс наследует и `CWinFormsView` передает `UserControl1` тип `CWinFormsView` конструктора и передает его. `UserControl1`— это пользовательский элемент управления в ControlLibrary1.dll.

[!code-cpp[NVC_MFC_Managed#1](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]

[!code-cpp[NVC_MFC_Managed#2](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]

## <a name="cwinformsviewgetcontrol"></a><a name="getcontrol"></a>CWinFormsView::GetControl

Извлекает указатель на элемент управления форм Windows.

```
System::Windows::Forms::Control^ GetControl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `System.Windows.Forms.Control`.

### <a name="remarks"></a>Remarks

Например, как использовать формы Windows, [см.](../../dotnet/using-a-windows-form-user-control-in-mfc.md)

## <a name="cwinformsviewoperator-control"></a><a name="operator_control"></a>CWinFormsView::Управление оператором

Отбрасывает тип в качестве указателя на элемент управления формами Windows.

```
operator System::Windows::Forms::Control^() const;
```

### <a name="remarks"></a>Remarks

Этот оператор позволяет передавать `CWinFormsView` представление функциям, которые принимают указатель на <xref:System.Windows.Forms.Control>управление типа форм Windows.

### <a name="example"></a>Пример

  Смотрите [CWinFormsView::GetControl](#getcontrol).

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md)<br/>
[Класс CWinFormsDialog](../../mfc/reference/cwinformsdialog-class.md)<br/>
[Класс CFormView](../../mfc/reference/cformview-class.md)
