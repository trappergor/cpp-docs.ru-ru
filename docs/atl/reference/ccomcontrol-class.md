---
title: "Класс CComControl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
helpviewer_keywords:
- control flags
- CComControlBase class, CComControl class
- stock properties, ATL
- CComControl class
- controls [ATL], control helper functions
- ambient properties
- controls [ATL], properties
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ae81e2b6beac11f94f8d117b004da2f8d0db8724
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccomcontrol-class"></a>Класс CComControl
Этот класс предоставляет методы для создания и управления ATL элементов управления.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T, class WinBase = CWindowImpl<T>>  
class ATL_NO_VTABLE CComControl : public CComControlBase,
    public WinBase;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, реализующий элемент управления.  
  
 *WinBase*  
 Базовый класс, реализующий Ранжирующие функции. По умолчанию используется значение [CWindowImpl](../../atl/reference/cwindowimpl-class.md).  
  
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
|[CComControl::FireOnChanged](#fireonchanged)|Уведомляет контейнера приемник измененного свойства элемента управления.|  
|[CComControl::FireOnRequestEdit](#fireonrequestedit)|Уведомляет контейнера приемник, свойство элемента управления изменением, и что объект запрашивает приемник дальнейших действий.|  
|[CComControl::MessageBox](#messagebox)|Этот метод используется для создания, отображения и работы окно сообщения.|  
  
## <a name="remarks"></a>Примечания  
 `CComControl`— Это набор полезных управления вспомогательные функции и необходимые данные членов для элементов управления ATL. При создании стандартного элемента управления или элемента управления DHTML, используя мастер элементов управления ATL, мастер автоматически будет наследовать класс от `CComControl`. `CComControl`Большинство методов из производного [CComControlBase](../../atl/reference/ccomcontrolbase-class.md).  
  
 Дополнительные сведения о создании элемента управления см. в разделе [учебник по ATL](../../atl/active-template-library-atl-tutorial.md). Дополнительные сведения о мастере проекта ATL см. в статье [создается проект ATL](../../atl/reference/creating-an-atl-project.md).  
  
 Демонстрацию `CComControl` методы и элементы данных. в разделе [CIRC](../../visual-cpp-samples.md) образца.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 `CComControl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="ccomcontrol"></a>CComControl::CComControl  
 Конструктор.  
  
```
CComControl();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase) конструктор, передавая `m_hWnd` данные-член наследуется через [CWindowImpl](../../atl/reference/cwindowimpl-class.md).  
  
##  <a name="controlqueryinterface"></a>CComControl::ControlQueryInterface  
 Извлекает указатель на запрошенный интерфейс.  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID запрашиваемого интерфейса.  
  
 `ppv`  
 [out] Указатель на указатель на интерфейс, определяемый `iid`, или **NULL** Если интерфейс не найден.  
  
### <a name="remarks"></a>Примечания  
 Обрабатывает интерфейсы только в таблицу сопоставлений COM.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]  
  
##  <a name="createcontrolwindow"></a>CComControl::CreateControlWindow  
 По умолчанию создает окна для элемента управления путем вызова `CWindowImpl::Create`.  
  
```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 [in] Дескриптор окна родительского или владельца. Необходимо указать действительный дескриптор окна. Окно управления сводится к области родительского окна.  
  
 `rcPos`  
 [in] Исходный размер и положение окна должен быть создан.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, если вы хотите сделать что-либо отличное от создания одного окна, например, чтобы создать два окна, один из которых становится инструментов для элемента управления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#16](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]  
  
##  <a name="fireonchanged"></a>CComControl::FireOnChanged  
 Уведомляет контейнера приемник измененного свойства элемента управления.  
  
```
HRESULT FireOnChanged(DISPID dispID);
```  
  
### <a name="parameters"></a>Параметры  
 *dispID*  
 [in] Идентификатор измененного свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Если класса элемента управления является производным от [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638), этот метод вызывает метод [CFirePropNotifyEvent::FireOnChanged](cfirepropnotifyevent-class.md#fireonchanged) известить всех подключенных `IPropertyNotifySink` интерфейсы, которые указанного элемента управления изменилось значение свойства. Если ваш класс элемента управления является производным от `IPropertyNotifySink`, этот метод возвращает `S_OK`. 
  
 Этот метод можно вызвать, даже если элемент управления не поддерживает точки подключения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#17](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]  
  
##  <a name="fireonrequestedit"></a>CComControl::FireOnRequestEdit  
 Уведомляет контейнера приемник, свойство элемента управления изменением, и что объект запрашивает приемник дальнейших действий.  
  
```
HRESULT FireOnRequestEdit(DISPID dispID);
```  
  
### <a name="parameters"></a>Параметры  
 *dispID*  
 [in] Идентификатор свойства будет изменен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Если класса элемента управления является производным от [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638), этот метод вызывает метод [CFirePropNotifyEvent::FireOnRequestEdit](cfirepropnotifyevent-class.md#fireonrequestedit) известить всех подключенных `IPropertyNotifySink` интерфейсы, которые указанного требуется изменить свойства элемента управления. Если ваш класс элемента управления является производным от `IPropertyNotifySink`, этот метод возвращает `S_OK`.  

  
 Этот метод можно вызвать, даже если элемент управления не поддерживает точки подключения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#18](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]  
  
##  <a name="messagebox"></a>CComControl::MessageBox  
 Этот метод используется для создания, отображения и работы окно сообщения.  
  
```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszText`  
 Текст, отображаемый в окне сообщения.  
  
 `lpszCaption`  
 Заголовок диалогового окна. Если значение NULL (по умолчанию), заголовок, используемый «Ошибка».  
  
 `nType`  
 Указывает содержимое и поведение диалогового окна. В разделе [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) запись в документации по пакету SDK Windows для получения списка доступных полей другое сообщение. Значение по умолчанию предоставляет простой **ОК** кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает целочисленное значение, указав одно из значений пунктов меню, перечисленных в разделе [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) документации по пакету Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 `MessageBox`полезно во время разработки и как простой способ отображения ошибок и предупреждений для пользователя.  
  
## <a name="see-also"></a>См. также  
 [Класс CWindowImpl](../../atl/reference/cwindowimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CComControlBase](../../atl/reference/ccomcontrolbase-class.md)   
 [Класс CComCompositeControl](../../atl/reference/ccomcompositecontrol-class.md)
