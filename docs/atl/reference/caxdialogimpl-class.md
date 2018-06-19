---
title: Класс CAxDialogImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAxDialogImpl class
- ATL, dialog boxes
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e3e1b7d4f88428060f4aa4d01180bce1e970b650
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365081"
---
# <a name="caxdialogimpl-class"></a>Класс CAxDialogImpl
Этот класс реализует диалоговое окно (модальные и немодальные), на котором размещены элементы управления ActiveX.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T, class TBase = CWindow>  
class ATL_NO_VTABLE CAxDialogImpl : public CDialogImplBaseT<TBase>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `CAxDialogImpl`.  
  
 *TBase*  
 Класс базового окна для **CDialogImplBaseT**.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAxDialogImpl::AdviseSinkMap](#advisesinkmap)|Этот метод используется для соединения или разъединения всех записей в схеме событий карты приемника объекта.|  
|[CAxDialogImpl::Create](#create)|Этот метод используется для создания немодального диалогового окна.|  
|[CAxDialogImpl::DestroyWindow](#destroywindow)|Этот метод вызывается для уничтожения немодального диалогового окна.|  
|[CAxDialogImpl::DoModal](#domodal)|Этот метод используется для создания модального диалогового окна.|  
|[CAxDialogImpl::EndDialog](#enddialog)|Этот метод вызывается для уничтожения модального диалогового окна.|  
|[CAxDialogImpl::GetDialogProc](#getdialogproc)|Этот метод вызывается для получения указателя на `DialogProc` функции обратного вызова.|  
|[CAxDialogImpl::GetIDD](#getidd)|Вызовите этот метод, чтобы получить идентификатор ресурса шаблона диалогового окна|  
|[CAxDialogImpl::IsDialogMessage](#isdialogmessage)|Этот метод вызывается для определения, предназначено ли сообщение для этого диалогового и обрабатывает сообщение, если он является.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание|  
|----------|-----------------|  
|[CAxDialogImpl::m_bModal](#m_bmodal)|Переменную, которая существует только в отладочной сборки и задано значение true, если является модальным диалоговым окном.|  
  
## <a name="remarks"></a>Примечания  
 `CAxDialogImpl` позволяет модальное или немодальное диалоговое окно создания. `CAxDialogImpl` предоставляет процедуру диалогового окна, который использует схему сообщений по умолчанию для направления сообщений для соответствующих обработчиков.  
  
 `CAxDialogImpl` является производным от `CDialogImplBaseT`, который в свою очередь является производным от *TBase* (по умолчанию `CWindow`) и `CMessageMap`.  
  
 Класс необходимо определить член прямой Международной, задает идентификатор ресурса шаблона диалогового окна Например, добавление объекта ATL диалогового окна с помощью **добавить класс** диалоговое окно автоматически добавляет следующую строку в класс:  
  
 [!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/caxdialogimpl-class_1.h)]  
  
 где `MyDialog` — **короткое имя** введенные в мастер диалоговых окон ATL.  
  
 В разделе [реализация диалогового](../../atl/implementing-a-dialog-box.md) для получения дополнительной информации.  
  
 Обратите внимание, что создан элемент управления ActiveX на модального диалогового окна с `CAxDialogImpl` не будет поддерживать сочетания клавиш. Для поддержки сочетания клавиш в диалоговом окне с `CAxDialogImpl`немодального диалогового окна, создать, с помощью собственного цикла обработки сообщений, используйте [CAxDialogImpl::IsDialogMessage](#isdialogmessage) после получения сообщения из очереди для обработки сочетание клавиш.  
  
 Дополнительные сведения о `CAxDialogImpl`, в разделе [часто задаваемые вопросы вложения элемента управления ATL](../../atl/atl-control-containment-faq.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CDialogImplBaseT`  
  
 `CAxDialogImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="advisesinkmap"></a>  CAxDialogImpl::AdviseSinkMap  
 Этот метод используется для соединения или разъединения всех записей в схеме событий карты приемника объекта.  
  
```
HRESULT AdviseSinkMap(bool bAdvise);
```  
  
### <a name="parameters"></a>Параметры  
 `bAdvise`  
 Значение true, если все записи приемника должны быть проигнорирована; приемник значение false, если все операции должны быть unadvised.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
##  <a name="create"></a>  CAxDialogImpl::Create  
 Этот метод используется для создания немодального диалогового окна.  
  
```
HWND Create(HWND hWndParent, LPARAM dwInitParam = NULL);
HWND Create(HWND hWndParent, RECT&, LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 [in] Дескриптор окна-владельца.  
  
 `dwInitParam`  
 [in] Указывает значение для передачи в диалоговом окне `lParam` параметр **WM_INITDIALOG** сообщения.  
  
 **RECT &AMP;**  
 Этот параметр не используется. Этот параметр передается с `CComControl`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор только что созданный диалоговым окном.  
  
### <a name="remarks"></a>Примечания  
 Это диалоговое окно предназначено, автоматически присоединяется к `CAxDialogImpl` объекта. Создание модального диалогового окна, вызовите [DoModal](#domodal).  
  
 Второй переопределение предоставляется только в том случае, чтобы можно было использовать диалоговые окна с [CComControl](../../atl/reference/ccomcontrol-class.md).  
  
##  <a name="destroywindow"></a>  CAxDialogImpl::DestroyWindow  
 Этот метод вызывается для уничтожения немодального диалогового окна.  
  
```
BOOL DestroyWindow();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если успешно уничтожении окна; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Не следует вызывать `DestroyWindow` для уничтожения модального диалогового окна. Вызовите [EndDialog](#enddialog) вместо него.  
  
##  <a name="domodal"></a>  CAxDialogImpl::DoModal  
 Этот метод используется для создания модального диалогового окна.  
  
```
INT_PTR DoModal(
  HWND hWndParent = ::GetActiveWindow(), 
  LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 [in] Дескриптор окна-владельца. Значение по умолчанию является значение, возвращаемое [GetActiveWindow](http://msdn.microsoft.com/library/windows/desktop/ms646292) функции Win32.  
  
 `dwInitParam`  
 [in] Указывает значение для передачи в диалоговом окне `lParam` параметр **WM_INITDIALOG** сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения значение `nRetCode` параметр, указанный в вызове [EndDialog](#enddialog); в противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
 Это диалоговое окно предназначено, автоматически присоединяется к `CAxDialogImpl` объекта.  
  
 Чтобы создать немодального диалогового окна, вызовите [создать](#create).  
  
##  <a name="enddialog"></a>  CAxDialogImpl::EndDialog  
 Этот метод вызывается для уничтожения модального диалогового окна.  
  
```
BOOL EndDialog(int nRetCode);
```  
  
### <a name="parameters"></a>Параметры  
 `nRetCode`  
 [in] Значение, возвращаемое по [DoModal](#domodal).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если диалоговое окно удаляется; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 `EndDialog` должен вызываться через процедуру диалогового окна. После удаления диалоговым окном Windows использует значение `nRetCode` как возвращаемое значение для `DoModal`, создавшего диалоговым окном.  
  
> [!NOTE]
>  Не следует вызывать `EndDialog` для уничтожения немодального диалогового окна. Вызовите [DestroyWindow](#destroywindow) вместо него.  
  
##  <a name="getdialogproc"></a>  CAxDialogImpl::GetDialogProc  
 Этот метод вызывается для получения указателя на `DialogProc` функции обратного вызова.  
  
```
virtual DLGPROC GetDialogProc();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на `DialogProc` функции обратного вызова.  
  
### <a name="remarks"></a>Примечания  
 `DialogProc` Функция — это функция обратного вызова, определяемые приложением.  
  
##  <a name="getidd"></a>  CAxDialogImpl::GetIDD  
 Вызовите этот метод, чтобы получить идентификатор ресурса шаблона диалогового окна  
  
```
int GetIDD();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает идентификатор ресурса шаблона диалогового окна  
  
##  <a name="isdialogmessage"></a>  CAxDialogImpl::IsDialogMessage  
 Этот метод вызывается для определения, предназначено ли сообщение для этого диалогового и обрабатывает сообщение, если он является.  
  
```
BOOL IsDialogMessage(LPMSG pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 `pMsg`  
 Указатель на [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) структуру, содержащую сообщение для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если сообщение был обработан, и FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот метод предназначен для вызова из в цикле обработки сообщений.  
  
##  <a name="m_bmodal"></a>  CAxDialogImpl::m_bModal  
 Переменную, которая существует только в отладочной сборки и задано значение true, если является модальным диалоговым окном.  
  
```
bool m_bModal;
```  
  
## <a name="see-also"></a>См. также  
 [CDialogImpl-класс](../../atl/reference/cdialogimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
