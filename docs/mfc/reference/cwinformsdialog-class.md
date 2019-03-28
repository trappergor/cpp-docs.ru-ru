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
ms.openlocfilehash: 1542f852a8fe3f05d81ae59efb8a522caae671fd
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565351"
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
.NET Framework пользовательский элемент управления, отображаемый в приложении MFC.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CWinFormsDialog::CWinFormsDialog](#cwinformsdialog)|Создает объект `CWinFormsDialog`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CWinFormsDialog::GetControl](#getcontrol)|Извлекает ссылку на пользовательский элемент управления Windows Forms.|
|[CWinFormsDialog::GetControlHandle](#getcontrolhandle)|Извлекает дескриптор окна для пользовательского элемента управления Windows Forms.|
|[CWinFormsDialog::OnInitDialog](#oninitdialog)|Инициализирует диалоговое окно MFC, создание и размещение пользовательского элемента управления Windows Forms на нем.|

### <a name="public-operators"></a>Открытые операторы

|name||
|----------|-|
|[CWinFormsDialog::operator-&gt;](#operator_-_gt)|Заменяет [CWinFormsDialog::GetControl](#getcontrol) в выражениях.|
|[CWinFormsDialog::operator TManagedControl ^](#operator-tmanagedcontrol-hat)|Приводит тип как ссылку на пользовательский элемент управления Windows Forms.|

## <a name="remarks"></a>Примечания

`CWinFormsDialog` является оболочкой для класса диалогового окна MFC ( [CDialog](../../mfc/reference/cdialog-class.md)), на котором размещается пользовательский элемент управления Windows Forms. Это позволяет отображать элементы управления .NET Framework в модальное или немодальное диалоговое окно MFC.

Дополнительные сведения об использовании Windows Forms, см. в разделе [использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) и [размещение элемента управления формы пользователя Windows в диалоговом окне MFC](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md).

## <a name="requirements"></a>Требования

**Заголовок:** afxwinforms.h

##  <a name="cwinformsdialog"></a>  CWinFormsDialog::CWinFormsDialog

Создает объект `CWinFormsDialog`.

```
CWinFormsDialog(UINT nIDTemplate = IDD);
```

### <a name="parameters"></a>Параметры

*nIDTemplate*<br/>
Содержит идентификатор ресурса шаблона диалогового окна поле. Использование редактора диалоговых окон для создания шаблона диалогового окна и сохранить его в файл скрипта ресурсов приложения. Дополнительные сведения о шаблонах диалоговое окно, см. в разделе [класса CDialog](../../mfc/reference/cdialog-class.md).

##  <a name="getcontrol"></a>  CWinFormsDialog::GetControl

Извлекает ссылку на пользовательский элемент управления Windows Forms.

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на элемент управления Windows Forms в диалоговом окне MFC.

##  <a name="getcontrolhandle"></a>  CWinFormsDialog::GetControlHandle

Извлекает дескриптор окна для пользовательского элемента управления Windows Forms.

```
inline HWND GetControlHandle() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает дескриптор окна для пользовательского элемента управления Windows Forms.

##  <a name="oninitdialog"></a>  CWinFormsDialog::OnInitDialog

Инициализирует диалоговое окно MFC, создание и размещение пользовательского элемента управления Windows Forms на нем.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Возвращаемое значение

Логическое значение, указывающее, является ли приложение установило фокус ввода к одному из элементов управления в диалоговом окне. Если `OnInitDialog` возвращает ненулевое значение, Windows устанавливает фокус ввода на первый элемент управления в диалоговом окне. Этот метод может возвращать значение 0 только в том случае, если приложение явно задает фокус ввода к одному из элементов управления в диалоговом окне.

### <a name="remarks"></a>Примечания

При создании в диалоговом окне MFC (с помощью [создать](../../mfc/reference/cdialog-class.md#create), [CreateIndirect](../../mfc/reference/cdialog-class.md#createindirect), или [DoModal](../../mfc/reference/cdialog-class.md#domodal) метод наследуется от [CDialog](../../mfc/reference/cdialog-class.md)), WM_ INITDIALOG будет отправлено, и этот метод вызывается. Он создает экземпляр элемента управления Windows Forms в диалоговом окне и изменяет размер окна, чтобы вместить в размер пользовательского элемента управления. Затем он размещает новый элемент управления в диалоговом окне MFC.

Переопределите эту функцию-член, если необходимо выполнять специальную обработку при инициализации диалоговое окно. Дополнительные сведения об использовании этого метода см. в разделе [CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog).

##  <a name="operator_-_gt"></a>  CWinFormsDialog::operator-&gt;

Заменяет [CWinFormsDialog::GetControl](#getcontrol) в выражениях.

```
inline TManagedControl^  operator->() const throw();
```

### <a name="remarks"></a>Примечания

Этот оператор предоставляет удобный синтаксис, который заменяет `GetControl` в выражениях.

Сведения об использовании Windows Forms, см. в разделе [использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="operator-tmanagedcontrol-hat"></a>  CWinFormsDialog::operator TManagedControl ^

Приводит тип как ссылку на пользовательский элемент управления Windows Forms.

```
inline operator TManagedControl^() const throw();
```

### <a name="remarks"></a>Примечания

Этот оператор приводит тип как ссылку на элемент управления Windows Forms. Он используется для передачи `CWinFormsDialog<TManagedControl>` диалоговое окно для функции, которые принимают указатель на объект элемента управления Windows Forms пользователя.

## <a name="see-also"></a>См. также

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CWinFormsView](../../mfc/reference/cwinformsview-class.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)
