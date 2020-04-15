---
title: Класс CDialogImpl
ms.date: 11/04/2016
f1_keywords:
- CDialogImpl
- ATLWIN/ATL::CDialogImpl
- ATLWIN/ATL::Create
- ATLWIN/ATL::DestroyWindow
- ATLWIN/ATL::DoModal
- ATLWIN/ATL::EndDialog
- ATLWIN/ATL::GetDialogProc
- ATLWIN/ATL::MapDialogRect
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::DialogProc
- ATLWIN/ATL::StartDialogProc
helpviewer_keywords:
- dialog boxes, ATL
- CDialogImpl class
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
ms.openlocfilehash: 900a312c97d7b83eac93a372be39a006b3c4344d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327051"
---
# <a name="cdialogimpl-class"></a>Класс CDialogImpl

Этот класс предоставляет методы для создания модального или бесрежимного диалогового окна.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class T,
    class TBase = CWindow>
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `CDialogImpl`.

*TBase*<br/>
Базовый класс вашего нового класса. Базовый класс по умолчанию — [CWindow](../../atl/reference/cwindow-class.md).

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[Создать](#create)|Создает бесрежимную диалоговую коробку.|
|[Destroywindow](#destroywindow)|Уничтожает бесрежимную диалоговую коробку.|
|[Domodal](#domodal)|Создает модальный диалоговый ящик.|
|[Enddialog](#enddialog)|Уничтожает модальный диалоговый ящик.|

### <a name="cdialogimplbaset-methods"></a>Методы CDialogImplBaseT

|||
|-|-|
|[GetDialogProc](#getdialogproc)|Возвращает текущую процедуру диалогового окна.|
|[MapDialogRect](#mapdialogrect)|Отображает единицы диалогового ящика указанного прямоугольника на экранные единицы (пиксели).|
|[OnFinalMessage](#onfinalmessage)|Вызывается после получения последнего сообщения, как правило, WM_NCDESTROY.|

### <a name="static-functions"></a>Статические функции

|||
|-|-|
|[ДиалогПрок](#dialogproc)|Обрабатывает сообщения, отправленные в диалоговую будку.|
|[StartDialogProc](#startdialogproc)|Вызывается при получении первого сообщения для обработки сообщений, отправленных в диалоговое окно.|

## <a name="remarks"></a>Remarks

С `CDialogImpl` помощью вы можете создать модальный или бесрежимный диалоговый ящик. `CDialogImpl`обеспечивает процедуру диалогового окна, которая использует карту сообщений по умолчанию для направления сообщений соответствующим обработчикам.

Деструктор `~CWindowImplRoot` базового класса гарантирует, что окно исчезло до уничтожения объекта.

`CDialogImpl`вытекает `CDialogImplBaseT`из, который, в `CWindowImplRoot`свою очередь, происходит от .

> [!NOTE]
> Ваш класс должен `IDD` определить элемент, определяющий идентификатор ресурса шаблона диалогов. Например, atL Project Wizard автоматически добавляет в свой класс следующую строку:

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]

где `MyDlg` **короткое имя,** внесенное на страницу **«Имена** волшебника».

|Дополнительные сведения|См.|
|--------------------------------|---------|
|Создание элементов управления|[Учебник по ATL](../../atl/active-template-library-atl-tutorial.md)|
|Использование диалоговые коробки в ATL|[Классы окон ATL](../../atl/atl-window-classes.md)|
|Мастер проектов ATL|[Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)|
|Диалоговые окна|[Диалог коробки](/windows/win32/dlgbox/dialog-boxes) и последующие темы в Windows SDK|

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="cdialogimplcreate"></a><a name="create"></a>CDialogImpl::Создание

Создает бесрежимную диалоговую коробку.

```
HWND Create(
    HWND hWndParent,
    LPARAM dwInitParam = NULL );

HWND Create(
    HWND hWndParent,
    RECT&,
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
(в) Ручка к окну владельца.

**RECT&** *rect* (в) структуре [RECT,](/previous-versions/dd162897\(v=vs.85\)) определяющей размер и положение диалога.

*dwInitParam*<br/>
(в) Определяет значение для передачи в поле диалога в параметре *lParam* WM_INITDIALOG сообщения.

### <a name="return-value"></a>Возвращаемое значение

Ручка к недавно созданному диалоговому ящику.

### <a name="remarks"></a>Remarks

Это диалоговое окно автоматически `CDialogImpl` прикрепляется к объекту. Чтобы создать модальный диалоговый ящик, позвоните [doModal](#domodal). Второй переопределение выше используется только с [CComControl](../../atl/reference/ccomcontrol-class.md).

## <a name="cdialogimpldestroywindow"></a><a name="destroywindow"></a>CDialogImpl: :DestroyWindow

Уничтожает бесрежимную диалоговую коробку.

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если диалоговая коробка была успешно уничтожена; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Возвращает TRUE, если диалоговая коробка была успешно уничтожена; в противном случае FALSE.

## <a name="cdialogimpldialogproc"></a><a name="dialogproc"></a>CDialogImpl: :DialogProc

Эта статическая функция реализует процедуру диалогового окна.

```
static LRESULT CALLBACK DialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
(в) Ручка к диалоговому ящику.

*uMsg*<br/>
(в) Сообщение отправлено в диалоговое окно.

*wParam*<br/>
(в) Дополнительная информация, соомнее сообщения.

*lParam*<br/>
(в) Дополнительная информация, соомнее сообщения.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если сообщение обработано; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

`DialogProc`использует карту сообщений по умолчанию для направления сообщений соответствующим обработчикам.

Можно переопределить, `DialogProc` чтобы обеспечить другой механизм обработки сообщений.

## <a name="cdialogimpldomodal"></a><a name="domodal"></a>CDialogImpl::DoModal

Создает модальный диалоговый ящик.

```
INT_PTR DoModal(
    HWND hWndParent = ::GetActiveWindow(),
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
(в) Ручка к окну владельца. Значение по умолчанию — это значение возврата функции [GetActiveWindow](/windows/win32/api/winuser/nf-winuser-getactivewindow) Win32.

*dwInitParam*<br/>
(в) Определяет значение для передачи в поле диалога в параметре *lParam* WM_INITDIALOG сообщения.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха значение параметра *nRetCode* указывается в вызове [к EndDialog.](#enddialog) В противном случае –1.

### <a name="remarks"></a>Remarks

Это диалоговое окно автоматически `CDialogImpl` прикрепляется к объекту.

Чтобы создать бесрежимный диалоговый ящик, вызов [Создать](#create).

## <a name="cdialogimplenddialog"></a><a name="enddialog"></a>CDialogImpl::EndDialog

Уничтожает модальный диалоговый ящик.

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>Параметры

*nRetCode*<br/>
(в) Значение, необходимое для возврата [CDialogImpl::DoModal](#domodal).

### <a name="return-value"></a>Возвращаемое значение

TRUE, если диалоговая будка уничтожена; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

`EndDialog`должны быть вызваны через процедуру диалога. После того, как диалоговое окно уничтожено, Windows использует значение `DoModal` *nRetCode* в качестве значения возврата для , который создал диалоговое окно.

> [!NOTE]
> Не звоните, `EndDialog` чтобы уничтожить безрежимный диалоговой ящик. Позвоните [CWindow: :DestroyWindow](../../atl/reference/cwindow-class.md#destroywindow) вместо.

## <a name="cdialogimplgetdialogproc"></a><a name="getdialogproc"></a>CDialogImpl::GetDialogProc

Возвращает `DialogProc`, текущая процедура диалогового окна.

```
virtual WNDPROC GetDialogProc();
```

### <a name="return-value"></a>Возвращаемое значение

Текущая процедура диалогового окна.

### <a name="remarks"></a>Remarks

Переопределить этот метод, чтобы заменить процедуру диалога с вашим собственным.

## <a name="cdialogimplmapdialogrect"></a><a name="mapdialogrect"></a>CDialogImpl:MapDialogRect

Преобразует (карты) единицы диалогового ящика указанного прямоугольника в единицы экрана (пиксели).

```
BOOL MapDialogRect(LPRECT lpRect);
```

### <a name="parameters"></a>Параметры

*lpRect*<br/>
Указывает на `CRect` объект или структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) которая должна получать координаты клиента обновления, которое заключает область обновления.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обновление удается; 0, если обновление не удается. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.

### <a name="remarks"></a>Remarks

Функция заменяет координаты `RECT` в указанной структуре на преобразованные координаты, что позволяет использовать структуру для создания диалогового окна или расположения элемента управления в диалоговом поле.

## <a name="cdialogimplonfinalmessage"></a><a name="onfinalmessage"></a>CDialogImpl::OnFinalMessage

Вызывается после получения последнего сообщения (обычно). `WM_NCDESTROY`

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
(в) Ручка к разрушенной окну.

### <a name="remarks"></a>Remarks

Обратите внимание, что если вы хотите автоматически удалить объект при уничтожении окна, вы можете **вызвать удалить это;** здесь.

## <a name="cdialogimplstartdialogproc"></a><a name="startdialogproc"></a>CDialogImpl::StartDialogProc

Вызывается только один раз, когда получено первое сообщение, для обработки сообщений, отправленных в диалоговое окно.

```
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
(в) Ручка к диалоговому ящику.

*uMsg*<br/>
(в) Сообщение отправлено в диалоговое окно.

*wParam*<br/>
(в) Дополнительная информация, соомнее сообщения.

*lParam*<br/>
(в) Дополнительная информация, соомнее сообщения.

### <a name="return-value"></a>Возвращаемое значение

Процедура окна.

### <a name="remarks"></a>Remarks

После первоначального `StartDialogProc`вызова, `DialogProc` устанавливается как диалоговая процедура, и дальнейшие звонки идут туда.

## <a name="see-also"></a>См. также раздел

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
