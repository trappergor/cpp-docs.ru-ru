---
title: Класс CDialogImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, ATL
- CDialogImpl class
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1780a4f77cce4812ebdb03ebc89936da0dc0d5d0
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767059"
---
# <a name="cdialogimpl-class"></a>CDialogImpl-класс

Этот класс предоставляет методы для создания модальное или немодальное диалоговое окно.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class T,
    class TBase = CWindow>
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>Параметры

*T*  
Ваш класс, производный от `CDialogImpl`.

*TBase*  
Базовый класс для нового класса. По умолчанию используется базовый класс [CWindow](../../atl/reference/cwindow-class.md).

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[Создание](#create)|Создает немодальное диалоговое окно.|
|[DestroyWindow](#destroywindow)|Уничтожает немодального диалогового окна.|
|[DoModal](#domodal)|Создает модальное диалоговое окно.|
|[EndDialog](#enddialog)|Уничтожает модальное диалоговое окно.|

### <a name="cdialogimplbaset-methods"></a>Методы CDialogImplBaseT

|||
|-|-|
|[GetDialogProc](#getdialogproc)|Возвращает текущий процедуру диалогового окна.|
|[MapDialogRect](#mapdialogrect)|Сопоставляет единицы диалогового окна, заданного прямоугольника единиц экрана (в пикселях).|
|[OnFinalMessage](#onfinalmessage)|Вызывается после получения последнего сообщения, обычно WM_NCDESTROY.|

### <a name="static-functions"></a>Статические функции

|||
|-|-|
|[DialogProc](#dialogproc)|Обрабатывает сообщения, отправленные в диалоговое окно.|
|[StartDialogProc](#startdialogproc)|Вызывается при получении первого сообщения для обработки сообщений, отправляемых в диалоговое окно.|

## <a name="remarks"></a>Примечания

С помощью `CDialogImpl` можно создать модальное или немодальное диалоговое окно. `CDialogImpl` предоставляет процедуру диалогового окна, который использует схему сообщений по умолчанию для направления сообщений соответствующих обработчиков.

Деструктор базового класса `~CWindowImplRoot` гарантирует, что окно вышедшего перед удалением объекта.

`CDialogImpl` является производным от `CDialogImplBaseT`, который, в свою очередь, наследуется от `CWindowImplRoot`.

> [!NOTE]
>  Необходимо определить класс `IDD` члена, указывающего идентификатор ресурса шаблона диалогового окна. Например мастер проектов ATL автоматически добавляет следующую строку в класс:

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]

где `MyDlg` — **короткое имя** введенные в мастере **имена** страницы.

|Дополнительные сведения о|См.|
|--------------------------------|---------|
|Создание элементов управления|[Учебник по ATL](../../atl/active-template-library-atl-tutorial.md)|
|С помощью диалоговых окон в ATL|[Классы окон ATL](../../atl/atl-window-classes.md)|
|Мастер проектов ATL|[Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)|
|Диалоговые окна|[Диалоговые окна](https://msdn.microsoft.com/library/windows/desktop/ms632588) и последующие разделы в пакете SDK для Windows|

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

##  <a name="create"></a>  CDialogImpl::Create

Создает немодальное диалоговое окно.

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

*hWndParent*  
[in] Дескриптор окна-владельца.

**RECT &** *rect*  
[in] Объект [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, указывающий размер и положение диалогового окна.

*dwInitParam*  
[in] Указывает значение для передачи в диалоговом окне *lParam* параметр WM_INITDIALOG сообщения.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор только что созданный диалоговое окно.

### <a name="remarks"></a>Примечания

Это диалоговое окно автоматически присоединяется ко `CDialogImpl` объекта. Для создания модального диалогового окна, вызовите [DoModal](#domodal). Второе переопределение выше используется только с [CComControl](../../atl/reference/ccomcontrol-class.md).

##  <a name="destroywindow"></a>  CDialogImpl::DestroyWindow

Уничтожает немодального диалогового окна.  

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если в диалоговом окне был успешно удален; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Возвращает значение TRUE, если диалоговое окно был успешно удален; в противном случае — значение FALSE.

##  <a name="dialogproc"></a>  CDialogImpl::DialogProc

Эта статическая функция реализует процедуру диалогового окна.  

```
static LRESULT CALLBACK DialogProc(
    HWND hWnd,  
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*hWnd*  
[in] Дескриптор в диалоговое окно.

*uMsg*  
[in] Сообщение, отправленное в диалоговое окно.

*wParam*  
[in] Дополнительные сведения, относящиеся к сообщению.

*lParam*  
[in] Дополнительные сведения, относящиеся к сообщению.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если сообщение обработано; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

`DialogProc` использует схему сообщений по умолчанию для направления сообщений соответствующих обработчиков.

Можно переопределить `DialogProc` для предоставления разных механизма для обработки сообщений.

##  <a name="domodal"></a>  CDialogImpl::DoModal

Создает модальное диалоговое окно.

```   
INT_PTR DoModal(  
    HWND hWndParent = ::GetActiveWindow(),   
    LPARAM dwInitParam = NULL); 
```

### <a name="parameters"></a>Параметры

*hWndParent*  
[in] Дескриптор окна-владельца. Значение по умолчанию — возвращаемое значение [GetActiveWindow](https://msdn.microsoft.com/library/windows/desktop/ms646292) функции Win32.

*dwInitParam*  
[in] Указывает значение для передачи в диалоговом окне *lParam* параметр WM_INITDIALOG сообщения.

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения значение *nRetCode* параметр, указанный в вызове [EndDialog](#enddialog). В противном случае — значение -1.

### <a name="remarks"></a>Примечания

Это диалоговое окно автоматически присоединяется ко `CDialogImpl` объекта.

Для создания немодального диалогового окна, вызовите [создать](#create).

##  <a name="enddialog"></a>  CDialogImpl::EndDialog

Уничтожает модальное диалоговое окно.

```   
BOOL EndDialog(int nRetCode); 
```

### <a name="parameters"></a>Параметры

*nRetCode*  
[in] Значение, возвращаемое по [CDialogImpl::DoModal](#domodal).

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если диалоговое окно уничтожается; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

`EndDialog` должен вызываться через процедуру диалогового окна. После уничтожения диалоговое окно Windows использует значение *nRetCode* как возвращаемое значение для `DoModal`, который создан в диалоговом окне.

> [!NOTE]
>  Не вызывайте `EndDialog` для уничтожения немодального диалогового окна. Вызовите [CWindow::DestroyWindow](../../atl/reference/cwindow-class.md#destroywindow) вместо этого.

##  <a name="getdialogproc"></a>  CDialogImpl::GetDialogProc

Возвращает `DialogProc`, процедура текущего диалогового окна.

```   
virtual WNDPROC GetDialogProc(); 
```

### <a name="return-value"></a>Возвращаемое значение

Текущее поле процедуру диалогового окна.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы заменить на собственные процедуру диалогового окна.

##  <a name="mapdialogrect"></a>  CDialogImpl::MapDialogRect

Преобразует единицы (maps) единицы указанного прямоугольника на экран диалогового окна (в пикселях).

```   
BOOL MapDialogRect(LPRECT lpRect); 
```

### <a name="parameters"></a>Параметры

*lpRect*  
Указывает на `CRect` объекта или [RECT](../../mfc/reference/rect-structure1.md) структуры, который принимает клиентских координат элемента обновление, которое включает в область обновления.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если обновление завершается успешно; 0 в случае сбоя обновления. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.

### <a name="remarks"></a>Примечания

Функция заменяет координаты в указанном `RECT` структура с преобразованные координаты, что позволяет структуре, который будет использоваться для создания диалогового окна или размещения элемента управления в диалоговом окне.

##  <a name="onfinalmessage"></a>  CDialogImpl::OnFinalMessage

Вызывается после получения последнего сообщения (обычно `WM_NCDESTROY`).

```   
virtual void OnFinalMessage(HWND hWnd); 
```

### <a name="parameters"></a>Параметры

*hWnd*  
[in] Дескриптор окна уничтожения.

### <a name="remarks"></a>Примечания

Обратите внимание, что если вы хотите автоматически удалить объект после уничтожения окна, можно вызвать **; удалить** здесь.

##  <a name="startdialogproc"></a>  CDialogImpl::StartDialogProc

Вызывается только один раз, при получении первого сообщения, для обработки сообщений, отправляемых в диалоговое окно.

```   
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,  
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam); 
```

### <a name="parameters"></a>Параметры

*hWnd*  
[in] Дескриптор в диалоговое окно.

*uMsg*  
[in] Сообщение, отправленное в диалоговое окно.

*wParam*  
[in] Дополнительные сведения, относящиеся к сообщению.

*lParam*  
[in] Дополнительные сведения, относящиеся к сообщению.

### <a name="return-value"></a>Возвращаемое значение

Процедура окна.

### <a name="remarks"></a>Примечания

После начального вызова `StartDialogProc`, `DialogProc` задано как процедуру диалогового окна, а также дополнительные вызовы перейти по ссылке.

## <a name="see-also"></a>См. также

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
[Общие сведения о классе](../../atl/atl-class-overview.md)