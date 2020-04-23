---
title: Класс CSplitButton
ms.date: 11/19/2018
f1_keywords:
- CSplitButton
- AFXCMN/CSplitButton
- AFXCMN/CSplitButton::CSplitButton
- AFXCMN/CSplitButton::Create
- AFXCMN/CSplitButton::SetDropDownMenu
- AFXCMN/CSplitButton::OnDropDown
helpviewer_keywords:
- CSplitButton [MFC], CSplitButton
- CSplitButton [MFC], Create
- CSplitButton [MFC], SetDropDownMenu
- CSplitButton [MFC], OnDropDown
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
ms.openlocfilehash: 38fceed1cc42ca0aac2e6ddaf145db273c95771d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753133"
---
# <a name="csplitbutton-class"></a>Класс CSplitButton

Класс `CSplitButton` представляет собой управление разделенной кнопкой. Элемент управления "кнопка разделения" реализует поведение по умолчанию, когда пользователь щелкает основную часть кнопки, и отображает раскрывающееся меню, когда пользователь щелкает раскрывающуюся стрелку кнопки.

## <a name="syntax"></a>Синтаксис

```
class CSplitButton : public CButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSplitButton::CSplitButton](#csplitbutton)|Формирует объект `CSplitButton`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSplitButton::Создание](#create)|Создает управление разделенной кнопкой с указанными `CSplitButton` стилями и прикрепляет его к текущему объекту.|
|[CSplitButton::SetDropDownMenu](#setdropdownmenu)|Устанавливает выпадающее меню, которое отображается при нажатии на стрелку выпадающих сплит-кнопки текущего управления кнопкой разделения.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CSplitbutton::OndropDown](#ondropdown)|Обрабатывает BCN_DROPDOWN уведомление, которое система отправляет, когда пользователь нажимает на выпадающую стрелку текущего управления кнопкой разделения.|

## <a name="remarks"></a>Remarks

Класс `CSplitButton` происходит от класса [CButton.](../../mfc/reference/cbutton-class.md) Управление кнопкой сплит-кнопки — это управление кнопкой, стиль которой BS_SPLITBUTTON. Он отображает пользовательское меню, когда пользователь нажимает на стрелку выпадения. Для получения дополнительной информации, см BS_SPLITBUTTON и BS_DEFSPLITBUTTON стилей в [баттонах стилей](/windows/win32/Controls/button-styles).

Следующая фигура изображает диалоговый ящик, содержащий управление пейджером и (1) управление кнопкой сплита. Стрелка с выпадения (2) уже нажата и отображается подменю (3).

![Диалоговое окно с кнопкой-разделителем и элементом управления страничного навигатора.](../../mfc/reference/media/splitbutton_pager.png "Диалоговое окно с кнопкой-разделителем и элементом управления страничного навигатора.")

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

`CSplitButton`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

Этот класс поддерживается в Windows Vista и позже.

Дополнительные требования к этому классу описаны в [требованиях к сборке для общих элементов управления Windows Vista.](../../mfc/build-requirements-for-windows-vista-common-controls.md)

## <a name="csplitbuttoncreate"></a><a name="create"></a>CSplitButton::Создание

Создает управление разделенной кнопкой с указанными `CSplitButton` стилями и прикрепляет его к текущему объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*dwStyle*|(в) Битовая комбинация (ИЛИ) стилей, которые должны быть применены к управлению. Для получения дополнительной информации [см.](../../mfc/reference/styles-used-by-mfc.md#button-styles)|
|*rect*|(в) Ссылка на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) содержащую положение и размер элемента управления.|
|*pParentWnd*|(в) Не-не-null указатель на [объект CWnd,](../../mfc/reference/cwnd-class.md) который является родительским окном элемента управления.|
|*nID*|(в) Идентификатор элемента управления.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

## <a name="csplitbuttoncsplitbutton"></a><a name="csplitbutton"></a>CSplitButton::CSplitButton

Формирует объект `CSplitButton`. Параметры конструктора указывают подменю, которое отображается при нажатии пользователя на выпадающую стрелку управления кнопкой разделения.

```
CSplitButton();

CSplitButton(
    UINT nMenuId,
    UINT nSubMenuId)
CSplitButton(CMenu* pMenu)
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*nMenuId*|(в) Идентификатор ресурса в панели меню.|
|*nSubMenuId*|(в) Идентификатор ресурса подменю.|
|*pMenu*|(в) Указатель на объект [CMenu,](../../mfc/reference/cmenu-class.md) который определяет подменю. Объект `CSplitButton` удаляет `CMenu` объект и связанный с `CSplitButton` ним HMENU, когда объект выходит за рамки.|

### <a name="remarks"></a>Remarks

Используйте [CSplitButton::Создание метода](#create) для создания разделения кнопки управления и прикрепить его к объекту. `CSplitButton`

## <a name="csplitbuttonondropdown"></a><a name="ondropdown"></a>CSplitbutton::OndropDown

Обрабатывает BCN_DROPDOWN уведомление, которое система отправляет, когда пользователь нажимает на выпадающую стрелку текущего управления кнопкой разделения.

```
afx_msg void OnDropDown(
    NMHDR* pNMHDR,
    LRESULT* pResult);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pNMHDR*|(в) Указатель на структуру [NMHDR,](/windows/win32/api/richedit/ns-richedit-nmhdr) содержащую информацию об [уведомлении BCN_DROPDOWN.](/windows/win32/Controls/bcn-dropdown)|
|*pResult*|(ваут) (Не используется; значение не возвращается.) Значение возврата [уведомления BCN_DROPDOWN.](/windows/win32/Controls/bcn-dropdown)|

### <a name="remarks"></a>Remarks

Когда пользователь нажимает стрелку выпадения кнопки на разделенной кнопке `OnDropDown` управления, система отправляет BCN_DROPDOWN сообщение уведомления, которое обрабатывает метод. Однако `CSplitButton` объект не пересылает уведомление BCN_DROPDOWN элемент управления, содержащего элемент управления сплит-кнопки. Следовательно, элемент элемента, содержащего элементуправления, не может поддерживать пользовательское действие в ответ на уведомление.

Для реализации пользовательского действия, которое поддерживает элемент управления, используйте `CSplitButton` объект [CButton](../../mfc/reference/cbutton-class.md) со стилем BS_SPLITBUTTON вместо объекта. Затем реализуйте обработчик `CButton` для уведомления BCN_DROPDOWN в объекте. Для получения дополнительной информации [см.](../../mfc/reference/styles-used-by-mfc.md#button-styles)

Для реализации пользовательского действия, которое поддерживает сама сплит-кнопка, используйте [отражение сообщений.](../../mfc/tn062-message-reflection-for-windows-controls.md) Выведить `CSplitButton` свой собственный класс из класса и назвать его, например, CMySplitButton. Затем добавьте следующую карту сообщений в приложение для обработки уведомления BCN_DROPDOWN:

```
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)
END_MESSAGE_MAP()
```

## <a name="csplitbuttonsetdropdownmenu"></a><a name="setdropdownmenu"></a>CSplitButton::SetDropDownMenu

Устанавливает выпадающее меню, которое отображается при нажатии на стрелку выпадающих сплит-кнопки текущего управления кнопкой разделения.

```cpp
void SetDropDownMenu(
    UINT nMenuId,
    UINT nSubMenuId);

void SetDropDownMenu(CMenu* pMenu);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*nMenuId*|(в) Идентификатор ресурса в панели меню.|
|*nSubMenuId*|(в) Идентификатор ресурса подменю.|
|*pMenu*|(в) Указатель на объект [CMenu,](../../mfc/reference/cmenu-class.md) который определяет подменю. Объект `CSplitButton` удаляет `CMenu` объект и связанный с `CSplitButton` ним HMENU, когда объект выходит за рамки.|

### <a name="remarks"></a>Remarks

Параметр *nMenuId* определяет панель меню, которая представляет собой горизонтальный список элементов меню. Параметр *nSubMenuId* — это нулевой индексный номер, который идентифицирует подменю, который представляет собой список элементов меню, связанных с каждым пунктом меню. Например, в типичном приложении есть меню, содержащее элементы меню," File, "Edit" и "Help". Пункт меню "Файл" имеет подменю, содержащее пункты меню "Открытый", "Закрыть" и "Выход". При нажатии стрелки сплит-кнопки управления элемент управления отображает указанное подменю, а не панель меню.

Следующая фигура изображает диалоговый ящик, содержащий управление пейджером и (1) управление кнопкой сплита. Стрелка с выпадения (2) уже нажата и отображается подменю (3).

![Диалоговое окно с кнопкой-разделителем и элементом управления страничного навигатора.](../../mfc/reference/media/splitbutton_pager.png "Диалоговое окно с кнопкой-разделителем и элементом управления страничного навигатора.")

### <a name="example"></a>Пример

Первое утверждение в следующем примере кода демонстрирует метод [CSplitButton::SetDropDownMenu.](#setdropdownmenu) Мы создали меню с редактором ресурсов Visual Studio, который автоматически назвал идентификатор панели меню, IDR_MENU1. Параметр *nSubMenuId,* который равен нулю, относится к единственному подменю меню бара.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс CSplitButton](../../mfc/reference/csplitbutton-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CButton](../../mfc/reference/cbutton-class.md)
