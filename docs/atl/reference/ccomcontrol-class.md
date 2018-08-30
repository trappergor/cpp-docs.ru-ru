---
title: Класс CComControl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComControl
- ATLCTL/ATL::CComControl
- ATLCTL/ATL::CComControl::CComControl
- ATLCTL/ATL::CComControl::ControlQueryInterface
- ATLCTL/ATL::CComControl::CreateControlWindow
- ATLCTL/ATL::CComControl::FireOnChanged
- ATLCTL/ATL::CComControl::FireOnRequestEdit
- ATLCTL/ATL::CComControl::MessageBox
dev_langs:
- C++
helpviewer_keywords:
- control flags
- CComControlBase class, CComControl class
- stock properties, ATL
- CComControl class
- controls [ATL], control helper functions
- ambient properties
- controls [ATL], properties
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0a2652730c981313ee3e168aca4a36a91fadde47
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43198459"
---
# <a name="ccomcontrol-class"></a>Класс CComControl
Этот класс предоставляет методы для создания и управления элементами управления ATL.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T, class WinBase = CWindowImpl<T>>  
class ATL_NO_VTABLE CComControl : public CComControlBase,
    public WinBase;
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Класс, реализация элемента управления.  
  
 *WinBase*  
 Базовый класс, реализующий функции управления окнами. По умолчанию используется [CWindowImpl](../../atl/reference/cwindowimpl-class.md).  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComControl::CComControl](#ccomcontrol)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComControl::ControlQueryInterface](#controlqueryinterface)|Извлекает указатель на запрошенный интерфейс.|  
|[CComControl::CreateControlWindow](#createcontrolwindow)|Создает окно для элемента управления.|  
|[CComControl::FireOnChanged](#fireonchanged)|Уведомляет приемника контейнера, измененного свойства элемента управления.|  
|[CComControl::FireOnRequestEdit](#fireonrequestedit)|Уведомляет приемника контейнера, что свойство элемента управления является изменением и что объект запрашивает приемника дальнейшие действия.|  
|[CComControl::MessageBox](#messagebox)|Этот метод используется для создания, отображения и работы окно сообщения.|  
  
## <a name="remarks"></a>Примечания  
 `CComControl` — Это набор полезных управления вспомогательные функции и важные данные-члены для элементов управления ATL. При создании стандартного элемента управления или элемент управления DHTML, с помощью мастера управления ATL, мастер автоматически будут производными от класса `CComControl`. `CComControl` является производным большинство методов из [CComControlBase](../../atl/reference/ccomcontrolbase-class.md).  
  
 Дополнительные сведения о создании элемента управления, см. в разделе [учебник по ATL](../../atl/active-template-library-atl-tutorial.md). Дополнительные сведения о мастере проекта ATL, см. в статье [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md).  
  
 С примером `CComControl` методы и элементы данных, см. в разделе [Кр](../../visual-cpp-samples.md) образца.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 `CComControl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="ccomcontrol"></a>  CComControl::CComControl  
 Конструктор.  
  
```
CComControl();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase) конструктор, передавая `m_hWnd` данные-член наследуется через [CWindowImpl](../../atl/reference/cwindowimpl-class.md).  
  
##  <a name="controlqueryinterface"></a>  CComControl::ControlQueryInterface  
 Извлекает указатель на запрошенный интерфейс.  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```  
  
### <a name="parameters"></a>Параметры  
 *IID*  
 [in] Идентификатор GUID запрашиваемого интерфейса.  
  
 *ppv*  
 [out] Указатель на указатель интерфейса, идентифицируемый *iid*, или значение NULL, если интерфейс не найден.  
  
### <a name="remarks"></a>Примечания  
 обрабатывает интерфейсы только в таблицу сопоставлений COM.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]  
  
##  <a name="createcontrolwindow"></a>  CComControl::CreateControlWindow  
 По умолчанию создает окно для элемента управления путем вызова `CWindowImpl::Create`.  
  
```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```  
  
### <a name="parameters"></a>Параметры  
 *hWndParent*  
 [in] Дескриптор окна родительского или владельца. Необходимо указать действительный дескриптор окна. Окно управления сводится к области его родительского окна.  
  
 *rcPos*  
 [in] Первоначальный размер и положение окна должен быть создан.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, если вы хотите сделать что-то отличное от создания одного окна, например, чтобы создать два окна, один из которых становится панель инструментов для элемента управления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#16](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]  
  
##  <a name="fireonchanged"></a>  CComControl::FireOnChanged  
 Уведомляет приемника контейнера, измененного свойства элемента управления.  
  
```
HRESULT FireOnChanged(DISPID dispID);
```  
  
### <a name="parameters"></a>Параметры  
 *dispID*  
 [in] Идентификатор измененного свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Если класса элемента управления является производным от [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink), этот метод вызывает метод [CFirePropNotifyEvent::FireOnChanged](cfirepropnotifyevent-class.md#fireonchanged) для уведомления о всех подключенных `IPropertyNotifySink` интерфейсы, указанного элемента управления Свойство изменилось. Если ваш класс элемента управления является производным от `IPropertyNotifySink`, этот метод возвращает значение S_OK. 
  
 Этот метод можно вызвать, даже если элемент управления не поддерживает точки подключения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#17](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]  
  
##  <a name="fireonrequestedit"></a>  CComControl::FireOnRequestEdit  
 Уведомляет приемника контейнера, что свойство элемента управления является изменением и что объект запрашивает приемника дальнейшие действия.  
  
```
HRESULT FireOnRequestEdit(DISPID dispID);
```  
  
### <a name="parameters"></a>Параметры  
 *dispID*  
 [in] Идентификатор свойства изменением.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Если класса элемента управления является производным от [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink), этот метод вызывает метод [CFirePropNotifyEvent::FireOnRequestEdit](cfirepropnotifyevent-class.md#fireonrequestedit) для уведомления о всех подключенных `IPropertyNotifySink` интерфейсы, указанного как изменить свойства элемента управления. Если ваш класс элемента управления является производным от `IPropertyNotifySink`, этот метод возвращает значение S_OK.  

  
 Этот метод можно вызвать, даже если элемент управления не поддерживает точки подключения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#18](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]  
  
##  <a name="messagebox"></a>  CComControl::MessageBox  
 Этот метод используется для создания, отображения и работы окно сообщения.  
  
```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszText*  
 Текст, отображаемый в окне сообщения.  
  
 *lpszCaption*  
 Заголовок диалогового окна. Если значение NULL (по умолчанию), заголовок, используемый «Error».  
  
 *nType*  
 Указывает содержимое и поведение диалогового окна. См. в разделе [MessageBox](/windows/desktop/api/winuser/nf-winuser-messagebox) запись в документации по Windows SDK для получения списка доступных полей другое сообщение. Значение по умолчанию предоставляет простой **ОК** кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение типа integer, указав одно из значений пунктов меню, списке [MessageBox](/windows/desktop/api/winuser/nf-winuser-messagebox) в документации по Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 `MessageBox` полезно как во время разработки, так и с легкостью для отображения ошибки или сообщение с предупреждением для пользователя.  
  
## <a name="see-also"></a>См. также  
 [Класс CWindowImpl](../../atl/reference/cwindowimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CComControlBase](../../atl/reference/ccomcontrolbase-class.md)   
 [Класс CComCompositeControl](../../atl/reference/ccomcompositecontrol-class.md)
