---
title: "CDialogImpl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab4bb1e04bd21900cdf8d8122af51547e79aea22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdialogimpl-class"></a>CDialogImpl-класс
Этот класс предоставляет методы для создания модального или немодального диалогового окна.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
 
template <class T,  
    class TBase = CWindow>  
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>  
 
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `CDialogImpl`.  
  
 *TBase*  
 Базовый класс к новому классу. Базовый класс по умолчанию — [CWindow](../../atl/reference/cwindow-class.md).  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Создание](#create)|Создает немодальное диалоговое окно.|  
|[DestroyWindow](#destroywindow)|Уничтожает немодального диалогового окна.|  
|[DoModal](#domodal)|Создает модальное диалоговое окно.|  
|[EndDialog](#enddialog)|Уничтожает модального диалогового окна.|  
  
### <a name="cdialogimplbaset-methods"></a>Методы CDialogImplBaseT  
  
|||  
|-|-|  
|[GetDialogProc](#getdialogproc)|Возвращает текущий процедуру диалогового окна.|  
|[MapDialogRect](#mapdialogrect)|Сопоставляет единицы диалогового окна в заданном прямоугольнике единицы экрана (в пикселях).|  
|[OnFinalMessage](#onfinalmessage)|Вызывается после получения последнего сообщения, обычно `WM_NCDESTROY`.|  
  
### <a name="static-functions"></a>Статические функции  
  
|||  
|-|-|  
|[DialogProc](#dialogproc)|Обрабатывает сообщения, отправленные в диалоговое окно.|  
|[StartDialogProc](#startdialogproc)|Вызывается при получении первого сообщения для обработки сообщений, отправляемых в диалоговое окно.|  
  
## <a name="remarks"></a>Примечания  
 С `CDialogImpl` можно создать диалоговое окно модальные и немодальные. `CDialogImpl`предоставляет процедуру диалогового окна, который использует схему сообщений по умолчанию для направления сообщений для соответствующих обработчиков.  
  
 Деструктор базового класса **~ CWindowImplRoot** гарантирует, что окно больше не находится перед удалением объекта.  
  
 `CDialogImpl`является производным от **CDialogImplBaseT**, который в свою очередь является производным от **CWindowImplRoot**.  
  
> [!NOTE]
>  Необходимо определить класс **прямой Международной** член, который задает идентификатор ресурса шаблона диалогового окна Например мастер проектов ATL автоматически добавляет следующую строку в класс:  
  
 [!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]  
  
 где `MyDlg` — **короткое имя** введено в окне мастера **имена** страницы.  
  
|Дополнительные сведения о|См.|  
|--------------------------------|---------|  
|Создание элементов управления|[Учебник по ATL](../../atl/active-template-library-atl-tutorial.md)|  
|С помощью диалоговых окон в ATL|[Классы окон ATL](../../atl/atl-window-classes.md)|  
|Мастер проектов ATL|[Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)|  
|Диалоговые окна|[Диалоговые окна](http://msdn.microsoft.com/library/windows/desktop/ms632588) и последующие разделы в Windows SDK|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="create"></a>CDialogImpl::Create  
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
 `hWndParent`  
 [in] Дескриптор окна-владельца.  
  
 **RECT &**`rect`  
 [in] Объект [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, определяя размер и положение диалогового окна.  
  
 `dwInitParam`  
 [in] Указывает значение для передачи в диалоговом окне **lParam** параметр **WM_INITDIALOG** сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор только что созданный диалоговым окном.  
  
### <a name="remarks"></a>Примечания  
 Это диалоговое окно предназначено, автоматически присоединяется к `CDialogImpl` объекта. Создание модального диалогового окна, вызовите [DoModal](#domodal). Второй переопределение выше используется только с [CComControl](../../atl/reference/ccomcontrol-class.md).  
  
##  <a name="destroywindow"></a>CDialogImpl::DestroyWindow  
 Уничтожает немодального диалогового окна.  
  
```  
 
BOOL DestroyWindow();

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если диалоговое окно было успешно уничтожено; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Возвращает **TRUE** Если диалоговое окно было успешно уничтожено; в противном случае **FALSE**.  
  
##  <a name="dialogproc"></a>CDialogImpl::DialogProc  
 Эта статическая функция реализует процедуру диалогового окна.  
  
```  
 
static LRESULT CALLBACK DialogProc(
    HWND hWnd,  
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam);

 
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 [in] Дескриптор диалоговым окном.  
  
 `uMsg`  
 [in] Сообщение, отправляемое диалоговым окном.  
  
 `wParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
 `lParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если сообщение обработано; в противном случае — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 `DialogProc`в схеме сообщений по умолчанию используется для направления сообщений для соответствующих обработчиков.  
  
 Можно переопределить `DialogProc` для предоставления разных механизма для обработки сообщений.  
  
##  <a name="domodal"></a>CDialogImpl::DoModal  
 Создает модальное диалоговое окно.  
  
```   
INT_PTR DoModal(  
    HWND hWndParent = ::GetActiveWindow(),   
    LPARAM dwInitParam = NULL); 
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 [in] Дескриптор окна-владельца. Значение по умолчанию является значение, возвращаемое [GetActiveWindow](http://msdn.microsoft.com/library/windows/desktop/ms646292) функции Win32.  
  
 `dwInitParam`  
 [in] Указывает значение для передачи в диалоговом окне **lParam** параметр **WM_INITDIALOG** сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения значение `nRetCode` параметр, указанный в вызове [EndDialog](#enddialog). В противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
 Это диалоговое окно предназначено, автоматически присоединяется к `CDialogImpl` объекта.  
  
 Чтобы создать немодального диалогового окна, вызовите [создать](#create).  
  
##  <a name="enddialog"></a>CDialogImpl::EndDialog  
 Уничтожает модального диалогового окна.  
  
```   
BOOL EndDialog(int nRetCode); 
```  
  
### <a name="parameters"></a>Параметры  
 `nRetCode`  
 [in] Значение, возвращаемое по [CDialogImpl::DoModal](#domodal).  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если диалоговое окно находится уничтожено; в противном случае — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 `EndDialog`необходимо вызывать при помощи процедуры диалога. После удаления диалоговым окном Windows использует значение `nRetCode` как возвращаемое значение для `DoModal`, создавшего диалоговым окном.  
  
> [!NOTE]
>  Не следует вызывать `EndDialog` для уничтожения немодального диалогового окна. Вызовите [CWindow::DestroyWindow](../../atl/reference/cwindow-class.md#destroywindow) вместо него.  
  
##  <a name="getdialogproc"></a>CDialogImpl::GetDialogProc  
 Возвращает `DialogProc`, процедура текущего диалогового окна.  
  
```   
virtual WNDPROC GetDialogProc(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий процедура диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод для замены вашу процедуру диалогового окна.  
  
##  <a name="mapdialogrect"></a>CDialogImpl::MapDialogRect  
 Преобразует единицы (maps) в заданном прямоугольнике экран единицы диалогового окна (в пикселях).  
  
```   
BOOL MapDialogRect(LPRECT lpRect); 
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указывает на `CRect` объекта или [RECT](../../mfc/reference/rect-structure1.md) структуру, получать клиентские координаты обновления, ограничивающий область обновления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если обновление завершается успешно; 0 в случае сбоя обновления. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.  
  
### <a name="remarks"></a>Примечания  
 Функция заменяет координаты в указанном `RECT` структура с преобразованные координаты, который позволяет сохранить структуру для создания диалогового окна или изменить расположение элемента управления в диалоговое окно.  
  
##  <a name="onfinalmessage"></a>CDialogImpl::OnFinalMessage  
 Вызывается после получения последнего сообщения (обычно `WM_NCDESTROY`).  
  
```   
virtual void OnFinalMessage(HWND hWnd); 
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 [in] Дескриптор окна уничтожении.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что если вы хотите автоматически удалить объект после уничтожения окна, можно вызвать `delete this;` здесь.  
  
##  <a name="startdialogproc"></a>CDialogImpl::StartDialogProc  
 Вызывается только один раз при получении первого сообщения для обработки сообщений, отправляемых в диалоговое окно.  
  
```   
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,  
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam); 
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 [in] Дескриптор диалоговым окном.  
  
 `uMsg`  
 [in] Сообщение, отправляемое диалоговым окном.  
  
 `wParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
 `lParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Процедуру окна.  
  
### <a name="remarks"></a>Примечания  
 После первого обращения к `StartDialogProc`, `DialogProc` задан как процедуру диалогового окна, а также дополнительные вызовы перейти по ссылке.  
  
## <a name="see-also"></a>См. также  
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)