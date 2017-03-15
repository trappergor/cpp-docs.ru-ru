---
title: "Класс CAxDialogImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAxDialogImpl
- ATL.CAxDialogImpl
- CAxDialogImpl
dev_langs:
- C++
helpviewer_keywords:
- CAxDialogImpl class
- ATL, dialog boxes
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 71e77ac6b8d2a89e384817020772bb855ce2d573
ms.lasthandoff: 02/24/2017

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
 `T`  
 Класс, производный от `CAxDialogImpl`.  
  
 *TBase*  
 Окно базовый класс для **CDialogImplBaseT**.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAxDialogImpl::AdviseSinkMap](#advisesinkmap)|Этот метод используется для соединения или разъединения всех записей в схеме событий карты приемника объекта.|  
|[CAxDialogImpl::Create](#create)|Этот метод используется для создания немодального диалогового окна.|  
|[CAxDialogImpl::DestroyWindow](#destroywindow)|Этот метод служит для уничтожения немодального диалогового окна.|  
|[CAxDialogImpl::DoModal](#domodal)|Этот метод используется для создания модального диалогового окна.|  
|[CAxDialogImpl::EndDialog](#enddialog)|Этот метод служит для уничтожения модального диалогового окна.|  
|[CAxDialogImpl::GetDialogProc](#getdialogproc)|Этот метод вызывается для получения указателя на `DialogProc` функции обратного вызова.|  
|[CAxDialogImpl::GetIDD](#getidd)|Вызовите этот метод, чтобы получить идентификатор ресурса шаблона диалогового окна|  
|[CAxDialogImpl::IsDialogMessage](#isdialogmessage)|Вызывать этот метод для определения, предназначено ли сообщение для этого диалогового и если это так, обработки сообщения.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAxDialogImpl::m_bModal](#m_bmodal)|Переменную, которая существует только в отладочных построений и задано значение true, если окно является модальным.|  
  
## <a name="remarks"></a>Примечания  
 `CAxDialogImpl`позволяет создать модальное или немодальное диалоговое окно. `CAxDialogImpl`предоставляет процедуру диалогового окна, который использует схему сообщений по умолчанию для направления сообщений для соответствующих обработчиков.  
  
 `CAxDialogImpl`является производным от `CDialogImplBaseT`, который в свою очередь является производным от *TBase* (по умолчанию `CWindow`) и `CMessageMap`.  
  
 Класс необходимо определить член IDD, задает идентификатор ресурса шаблона диалогового окна Например, добавление объекта диалогового окна ATL с помощью **добавить класс** диалоговое окно автоматически добавляет следующую строку в класс:  
  
 [!code-cpp[NVC_ATL_Windowing&#41;](../../atl/codesnippet/cpp/caxdialogimpl-class_1.h)]  
  
 где `MyDialog` — **короткое имя** в мастере ATL диалоговое окно.  
  
 В разделе [реализация диалогового](../../atl/implementing-a-dialog-box.md) подробнее.  
  
 Обратите внимание, что создан элемент управления ActiveX на модального диалогового окна с `CAxDialogImpl` не будет поддерживать сочетания клавиш. Для поддержки сочетаний клавиш в диалоговом окне с `CAxDialogImpl`, создание немодального диалогового окна и с использованием собственного цикла обработки сообщений, используйте [CAxDialogImpl::IsDialogMessage](#isdialogmessage) после получения сообщения из очереди для обработки сочетания клавиш.  
  
 Дополнительные сведения о `CAxDialogImpl`, в разделе [ATL управления вложения часто задаваемые вопросы о](../../atl/atl-control-containment-faq.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CDialogImplBaseT`  
  
 `CAxDialogImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="a-nameadvisesinkmapa--caxdialogimpladvisesinkmap"></a><a name="advisesinkmap"></a>CAxDialogImpl::AdviseSinkMap  
 Этот метод используется для соединения или разъединения всех записей в схеме событий карты приемника объекта.  
  
```
HRESULT AdviseSinkMap(bool bAdvise);
```  
  
### <a name="parameters"></a>Параметры  
 `bAdvise`  
 Значение true, если все операции приемника знать; приемник значение false, если все операции должны быть unadvised.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="a-namecreatea--caxdialogimplcreate"></a><a name="create"></a>CAxDialogImpl::Create  
 Этот метод используется для создания немодального диалогового окна.  
  
```
HWND Create(HWND hWndParent, LPARAM dwInitParam = NULL);
HWND Create(HWND hWndParent, RECT&, LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 [in] Дескриптор окна-владельца.  
  
 `dwInitParam`  
 [in] Указывает значение для передачи в диалоговом окне `lParam` параметр **WM_INITDIALOG** сообщение.  
  
 **RECT &**  
 Этот параметр не используется. Этот параметр передается с `CComControl`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор только что созданный диалоговым окном.  
  
### <a name="remarks"></a>Примечания  
 Автоматически присоединяется к этому диалоговому окну `CAxDialogImpl` объекта. Для создания модального диалогового окна, вызовите [DoModal](#domodal).  
  
 Второй переопределение предоставляется только в том случае, чтобы можно было использовать диалоговые окна с [CComControl](../../atl/reference/ccomcontrol-class.md).  
  
##  <a name="a-namedestroywindowa--caxdialogimpldestroywindow"></a><a name="destroywindow"></a>CAxDialogImpl::DestroyWindow  
 Этот метод служит для уничтожения немодального диалогового окна.  
  
```
BOOL DestroyWindow();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если успешно уничтожении окна; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Не следует вызывать `DestroyWindow` для уничтожения модального диалогового окна. Вызов [EndDialog](#enddialog) вместо.  
  
##  <a name="a-namedomodala--caxdialogimpldomodal"></a><a name="domodal"></a>CAxDialogImpl::DoModal  
 Этот метод используется для создания модального диалогового окна.  
  
```
INT_PTR DoModal(
  HWND hWndParent = ::GetActiveWindow(), 
  LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 [in] Дескриптор окна-владельца. Значение по умолчанию — значение, возвращаемое [GetActiveWindow](http://msdn.microsoft.com/library/windows/desktop/ms646292) функции Win32.  
  
 `dwInitParam`  
 [in] Указывает значение для передачи в диалоговом окне `lParam` параметр **WM_INITDIALOG** сообщение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения значение `nRetCode` параметр, указанный в вызове [EndDialog](#enddialog); в противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
 Автоматически присоединяется к этому диалоговому окну `CAxDialogImpl` объекта.  
  
 Чтобы создать немодального диалогового окна, вызовите [создать](#create).  
  
##  <a name="a-nameenddialoga--caxdialogimplenddialog"></a><a name="enddialog"></a>CAxDialogImpl::EndDialog  
 Этот метод служит для уничтожения модального диалогового окна.  
  
```
BOOL EndDialog(int nRetCode);
```  
  
### <a name="parameters"></a>Параметры  
 `nRetCode`  
 [in] Значения, возвращаемые [DoModal](#domodal).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если диалоговое окно удаляется; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 `EndDialog`должен вызываться через процедуру диалогового окна. После уничтожения диалоговое окно Windows использует значение `nRetCode` как возвращаемое значение для `DoModal`, создавшего диалоговое окно.  
  
> [!NOTE]
>  Не следует вызывать `EndDialog` для уничтожения немодального диалогового окна. Вызов [DestroyWindow](#destroywindow) вместо.  
  
##  <a name="a-namegetdialogproca--caxdialogimplgetdialogproc"></a><a name="getdialogproc"></a>CAxDialogImpl::GetDialogProc  
 Этот метод вызывается для получения указателя на `DialogProc` функции обратного вызова.  
  
```
virtual DLGPROC GetDialogProc();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на `DialogProc` функции обратного вызова.  
  
### <a name="remarks"></a>Примечания  
 `DialogProc` Функция является функцией обратного вызова, определяемые приложением.  
  
##  <a name="a-namegetidda--caxdialogimplgetidd"></a><a name="getidd"></a>CAxDialogImpl::GetIDD  
 Вызовите этот метод, чтобы получить идентификатор ресурса шаблона диалогового окна  
  
```
int GetIDD();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает идентификатор ресурса шаблона диалогового окна  
  
##  <a name="a-nameisdialogmessagea--caxdialogimplisdialogmessage"></a><a name="isdialogmessage"></a>CAxDialogImpl::IsDialogMessage  
 Вызывать этот метод для определения, предназначено ли сообщение для этого диалогового и если это так, обработки сообщения.  
  
```
BOOL IsDialogMessage(LPMSG pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 `pMsg`  
 Указатель на [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) структуру, содержащую сообщения для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если сообщения был обработан, и FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот метод предназначен для вызова из в цикл обработки сообщений.  
  
##  <a name="a-namembmodala--caxdialogimplmbmodal"></a><a name="m_bmodal"></a>CAxDialogImpl::m_bModal  
 Переменную, которая существует только в отладочных построений и задано значение true, если окно является модальным.  
  
```
bool m_bModal;
```  
  
## <a name="see-also"></a>См. также  
 [CDialogImpl-класс](../../atl/reference/cdialogimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

