---
title: Класс CAxDialogImpl
ms.date: 11/04/2016
f1_keywords:
- CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl::AdviseSinkMap
- ATLWIN/ATL::CAxDialogImpl::Create
- ATLWIN/ATL::CAxDialogImpl::DestroyWindow
- ATLWIN/ATL::CAxDialogImpl::DoModal
- ATLWIN/ATL::CAxDialogImpl::EndDialog
- ATLWIN/ATL::CAxDialogImpl::GetDialogProc
- ATLWIN/ATL::CAxDialogImpl::GetIDD
- ATLWIN/ATL::CAxDialogImpl::IsDialogMessage
- ATLWIN/ATL::CAxDialogImpl::m_bModal
helpviewer_keywords:
- CAxDialogImpl class
- ATL, dialog boxes
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
ms.openlocfilehash: 852656b33eca1a8c87c6931b58cd49c0c41fe3dc
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2019
ms.locfileid: "54893643"
---
# <a name="caxdialogimpl-class"></a>Класс CAxDialogImpl

Этот класс реализует диалоговое окно (модальное или немодальное), на котором размещены элементы управления ActiveX.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class T, class TBase = CWindow>
class ATL_NO_VTABLE CAxDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `CAxDialogImpl`.

*TBase*<br/>
Класс базового окна для `CDialogImplBaseT`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CAxDialogImpl::AdviseSinkMap](#advisesinkmap)|Этот метод используется для соединения или разъединения всех записей в схеме событий объекта приемника карты.|
|[CAxDialogImpl::Create](#create)|Этот метод используется для создания немодального диалогового окна.|
|[CAxDialogImpl::DestroyWindow](#destroywindow)|Этот метод служит для уничтожения немодального диалогового окна.|
|[CAxDialogImpl::DoModal](#domodal)|Этот метод используется для создания модального диалогового окна.|
|[CAxDialogImpl::EndDialog](#enddialog)|Этот метод служит для уничтожения модальное диалоговое окно.|
|[CAxDialogImpl::GetDialogProc](#getdialogproc)|Вызовите этот метод для получения указателя на `DialogProc` функцию обратного вызова.|
|[CAxDialogImpl::GetIDD](#getidd)|Вызовите этот метод, чтобы получить идентификатор ресурса шаблона диалогового окна|
|[CAxDialogImpl::IsDialogMessage](#isdialogmessage)|Вызовите этот метод, чтобы определить, предназначен ли сообщение для это диалоговое окно и, в противном случае обработки сообщения.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CAxDialogImpl::m_bModal](#m_bmodal)|Переменную, которая существует только в отладочной сборки и задано значение true, если окно является модальным.|

## <a name="remarks"></a>Примечания

`CAxDialogImpl` позволяет создать модальное или немодальное диалоговое окно. `CAxDialogImpl` предоставляет процедуру диалогового окна, который использует схему сообщений по умолчанию для направления сообщений соответствующих обработчиков.

`CAxDialogImpl` является производным от `CDialogImplBaseT`, который, в свою очередь, наследуется от *TBase* (по умолчанию `CWindow`) и `CMessageMap`.

Ваш класс должен определить член IDD, указывающее идентификатор ресурса шаблона диалогового окна. Например, добавление объекта ATL диалоговое окно с помощью **Добавление класса** диалоговое окно автоматически добавляет следующую строку в класс:

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/caxdialogimpl-class_1.h)]

где `MyDialog` — **короткое имя** введенные в мастере ATL диалоговое окно.

См. в разделе [реализация диалогового окна](../../atl/implementing-a-dialog-box.md) Дополнительные сведения.

Обратите внимание, что элемент управления ActiveX на модальное диалоговое окно создания с `CAxDialogImpl` не будет поддерживать сочетания клавиш. Для поддержки сочетаний клавиш в диалоговом окне, созданных с помощью `CAxDialogImpl`, создание немодального диалогового окна и с помощью собственного цикла обработки сообщений, используйте [CAxDialogImpl::IsDialogMessage](#isdialogmessage) после получения сообщения из очереди для обработки сочетание клавиш.

Дополнительные сведения о `CAxDialogImpl`, см. в разделе [ATL управления вложения часто задаваемые вопросы о](../../atl/atl-control-containment-faq.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMessageMap](../../atl/reference/cmessagemap-class.md)

`TBase`

`CWindowImplRoot`

`CDialogImplBaseT`

`CAxDialogImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

##  <a name="advisesinkmap"></a>  CAxDialogImpl::AdviseSinkMap

Этот метод используется для соединения или разъединения всех записей в схеме событий объекта приемника карты.

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>Параметры

*bAdvise*<br/>
Значение true, если все записи в качестве приемника, которому необходимо предоставить рекомендацию; приемник значение false, если все операции должны быть негативной рекомендации.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="create"></a>  CAxDialogImpl::Create

Этот метод используется для создания немодального диалогового окна.

```
HWND Create(HWND hWndParent, LPARAM dwInitParam = NULL);
HWND Create(HWND hWndParent, RECT&, LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
[in] Дескриптор окна-владельца.

*dwInitParam*<br/>
[in] Указывает значение для передачи в диалоговом окне *lParam* параметр WM_INITDIALOG сообщения.

*RECT &AMP;*<br/>
Этот параметр не используется. Этот параметр передается с `CComControl`.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор только что созданный диалоговое окно.

### <a name="remarks"></a>Примечания

Это диалоговое окно автоматически присоединяется ко `CAxDialogImpl` объекта. Для создания модального диалогового окна, вызовите [DoModal](#domodal).

Второе переопределение предоставляется только в том случае, чтобы можно было использовать диалоговые окна с [CComControl](../../atl/reference/ccomcontrol-class.md).

##  <a name="destroywindow"></a>  CAxDialogImpl::DestroyWindow

Этот метод служит для уничтожения немодального диалогового окна.

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно уничтожении окна; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Не вызывайте `DestroyWindow` для уничтожения модальное диалоговое окно. Вызовите [EndDialog](#enddialog) вместо этого.

##  <a name="domodal"></a>  CAxDialogImpl::DoModal

Этот метод используется для создания модального диалогового окна.

```
INT_PTR DoModal(
    HWND hWndParent = ::GetActiveWindow(),
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
[in] Дескриптор окна-владельца. Значение по умолчанию — возвращаемое значение [GetActiveWindow](/windows/desktop/api/winuser/nf-winuser-getactivewindow) функции Win32.

*dwInitParam*<br/>
[in] Указывает значение для передачи в диалоговом окне *lParam* параметр WM_INITDIALOG сообщения.

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения значение *nRetCode* параметр, указанный в вызове [EndDialog](#enddialog); в противном случае — значение -1.

### <a name="remarks"></a>Примечания

Это диалоговое окно автоматически присоединяется ко `CAxDialogImpl` объекта.

Для создания немодального диалогового окна, вызовите [создать](#create).

##  <a name="enddialog"></a>  CAxDialogImpl::EndDialog

Этот метод служит для уничтожения модальное диалоговое окно.

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>Параметры

*nRetCode*<br/>
[in] Значение, возвращаемое по [DoModal](#domodal).

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если диалоговое окно уничтожается; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

`EndDialog` должен вызываться через процедуру диалогового окна. После уничтожения диалоговое окно Windows использует значение *nRetCode* как возвращаемое значение для `DoModal`, который создан в диалоговом окне.

> [!NOTE]
>  Не вызывайте `EndDialog` для уничтожения немодального диалогового окна. Вызовите [DestroyWindow](#destroywindow) вместо этого.

##  <a name="getdialogproc"></a>  CAxDialogImpl::GetDialogProc

Вызовите этот метод для получения указателя на `DialogProc` функцию обратного вызова.

```
virtual DLGPROC GetDialogProc();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на `DialogProc` функцию обратного вызова.

### <a name="remarks"></a>Примечания

`DialogProc` Функция является функцией обратного вызова, определяемые приложением.

##  <a name="getidd"></a>  CAxDialogImpl::GetIDD

Вызовите этот метод, чтобы получить идентификатор ресурса шаблона диалогового окна.

```
int GetIDD();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает идентификатор ресурса шаблона диалогового окна.

##  <a name="isdialogmessage"></a>  CAxDialogImpl::IsDialogMessage

Вызовите этот метод, чтобы определить, предназначен ли сообщение для это диалоговое окно и, в противном случае обработки сообщения.

```
BOOL IsDialogMessage(LPMSG pMsg);
```

### <a name="parameters"></a>Параметры

*pMsg*<br/>
Указатель на [MSG](/windows/desktop/api/winuser/ns-winuser-msg) структуру, содержащую сообщения для проверки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если сообщение был обработан, и FALSE в противном случае.

### <a name="remarks"></a>Примечания

Этот метод предназначен для вызова из в цикл обработки сообщений.

##  <a name="m_bmodal"></a>  CAxDialogImpl::m_bModal

Переменную, которая существует только в отладочной сборки и задано значение true, если окно является модальным.

```
bool m_bModal;
```

## <a name="see-also"></a>См. также

[Класс CDialogImpl](../../atl/reference/cdialogimpl-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
