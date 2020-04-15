---
title: Класс CWinFormsDialog
ms.date: 03/27/2019
f1_keywords:
- CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::GetControl
- AFXWINFORMS/CWinFormsDialog::GetControlHandle
- AFXWINFORMS/CWinFormsDialog::OnInitDialog
helpviewer_keywords:
- CWinFormsDialog [MFC], CWinFormsDialog
- CWinFormsDialog [MFC], GetControl
- CWinFormsDialog [MFC], GetControlHandle
- CWinFormsDialog [MFC], OnInitDialog
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
ms.openlocfilehash: 3772033df59e065cedca61012cd479c812cf5b66
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367428"
---
# <a name="cwinformsdialog-class"></a>Класс CWinFormsDialog

Программа-оболочка для класса диалогового окна MFC, в котором размещается пользовательский элемент управления Windows Forms.

## <a name="syntax"></a>Синтаксис

```
template <typename TManagedControl>
class CWinFormsDialog :
    public CDialog
```

#### <a name="parameters"></a>Параметры

*TManagedControl*<br/>
Пользовательский контроль .NET Framework будет отображаться в приложении MFC.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CWinFormsДиалог::CWinFormsДиалог](#cwinformsdialog)|Формирует объект `CWinFormsDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWinFormsДиалог::GetControl](#getcontrol)|Извлекает ссылку на пользовательский контроль Форм Windows.|
|[CWinFormsДиалог::GetControlHandle](#getcontrolhandle)|Извлекает ручку окна в управление пользователя Windows Forms.|
|[CWinFormsDialog::OnInitDialog](#oninitdialog)|Инициализирует диалоговую коробку MFC, создавая и размещая на нем пользовательский контроль Форм Windows.|

### <a name="public-operators"></a>Открытые операторы

|Имя||
|----------|-|
|[CWinFormsДиалог:Оператор -&gt;](#operator_-_gt)|Заменяет [CWinFormsDialog::GetControl](#getcontrol) в выражениях.|
|[CWinFormsDialog::оператор TManagedControl](#operator-tmanagedcontrol-hat)|Отбрасывает тип в качестве ссылки на пользовательский контроль Форм Windows.|

## <a name="remarks"></a>Remarks

`CWinFormsDialog`— это обертка для класса диалога MFC [(CDialog),](../../mfc/reference/cdialog-class.md)в котором размещается пользовательский контроль форм Windows. Это позволяет отображать элементы управления .NET Framework в модальном или безспособном диалоговом окне MFC.

Для получения дополнительной информации об использовании форм Windows, [см. С помощью управления пользователями формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) и [хостинг амебь пользователя формы Windows в качестве MFC Dialog Box](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md).

## <a name="requirements"></a>Требования

**Заголовок:** afxwinforms.h

## <a name="cwinformsdialogcwinformsdialog"></a><a name="cwinformsdialog"></a>CWinFormsДиалог::CWinFormsДиалог

Формирует объект `CWinFormsDialog`.

```
CWinFormsDialog(UINT nIDTemplate = IDD);
```

### <a name="parameters"></a>Параметры

*nIDTemplate*<br/>
Содержит идентификатор ресурса шаблона диалогового окна. Используйте редактор диалогов для создания шаблона диалогов и его хранения в файле скрипта ресурса приложения. Для получения дополнительной информации о [CDialog Class](../../mfc/reference/cdialog-class.md)шаблонах диалога см.

## <a name="cwinformsdialoggetcontrol"></a><a name="getcontrol"></a>CWinFormsДиалог::GetControl

Извлекает ссылку на пользовательский контроль Форм Windows.

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на элемент управления windows Forms в диалоговом окне MFC.

## <a name="cwinformsdialoggetcontrolhandle"></a><a name="getcontrolhandle"></a>CWinFormsДиалог::GetControlHandle

Извлекает ручку окна в управление пользователя Windows Forms.

```
inline HWND GetControlHandle() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку окна в управление пользователя Windows Forms.

## <a name="cwinformsdialogoninitdialog"></a><a name="oninitdialog"></a>CWinFormsDialog::OnInitDialog

Инициализирует диалоговую коробку MFC, создавая и размещая на нем пользовательский контроль Форм Windows.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Возвращаемое значение

Значение Boolean, которое определяет, установило ли приложение входной фокус на один из элементов управления в диалоговом поле. Если `OnInitDialog` возвращается ненулевой, Windows устанавливает вхотворный фокус для первого элемента управления в диалоговом поле. Этот метод может вернуть 0 только в том случае, если приложение явно установило фокус ввода на один из элементов управления в диалоговом поле.

### <a name="remarks"></a>Remarks

При создании диалогового окна MFC (с помощью [Create,](../../mfc/reference/cdialog-class.md#create) [CreateIndirect](../../mfc/reference/cdialog-class.md#createindirect)или [DoModal](../../mfc/reference/cdialog-class.md#domodal) метода, унаследованного от [CDialog),](../../mfc/reference/cdialog-class.md)отправляется WM_INITDIALOG сообщение, и этот метод называется. Он создает экземпляр управления формами Windows в диалоговом поле и регулирует размер диалогового окна для размещения для размера управления пользователем. Затем он принимает новый контроль в диалоговом окне MFC.

Переопределить эту функцию члена, если вам нужно выполнить специальную обработку, когда диалоговый ящик инициализирован. Для получения дополнительной информации об использовании этого метода, [см. CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog).

## <a name="cwinformsdialogoperator--gt"></a><a name="operator_-_gt"></a>CWinFormsДиалог:Оператор -&gt;

Заменяет [CWinFormsDialog::GetControl](#getcontrol) в выражениях.

```
inline TManagedControl^  operator->() const throw();
```

### <a name="remarks"></a>Remarks

Этот оператор обеспечивает удобный синтаксис, который заменяет `GetControl` в выражениях.

Для получения информации об использовании форм Windows, [см.](../../dotnet/using-a-windows-form-user-control-in-mfc.md)

## <a name="cwinformsdialogoperator-tmanagedcontrol"></a><a name="operator-tmanagedcontrol-hat"></a>CWinFormsDialog::оператор TManagedControl

Отбрасывает тип в качестве ссылки на пользовательский контроль Форм Windows.

```
inline operator TManagedControl^() const throw();
```

### <a name="remarks"></a>Remarks

Этот оператор отбрасывает тип в качестве ссылки на элемент управления Windows Forms. Он используется для `CWinFormsDialog<TManagedControl>` передачи диалогового окна функциям, принимающим указатель на объект управления пользователем Windows Forms.

## <a name="see-also"></a>См. также раздел

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CWinFormsView](../../mfc/reference/cwinformsview-class.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)
