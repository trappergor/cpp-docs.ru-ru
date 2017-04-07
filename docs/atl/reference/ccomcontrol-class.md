---
title: "Класс CComControl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
caps.latest.revision: 22
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 387d38f89e8d783c7ae85c2ab960d5e59c1c4009
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcontrol-class"></a>Класс CComControl
Этот класс предоставляет методы для создания и управления элементами управления ATL..  
  
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
 Базовый класс, реализующий функций управления окнами. По умолчанию [CWindowImpl](../../atl/reference/cwindowimpl-class.md).  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComControl::CComControl](#ccomcontrol)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComControl::ControlQueryInterface](#controlqueryinterface)|Извлекает указатель на запрошенный интерфейс.|  
|[CComControl::CreateControlWindow](#createcontrolwindow)|Создает окно для элемента управления.|  
|[CComControl::FireOnChanged](#fireonchanged)|Уведомляет контейнера приемник измененного свойства элемента управления.|  
|[CComControl::FireOnRequestEdit](#fireonrequestedit)|Уведомляет приемника контейнера, что свойства элемента управления будет изменен и что объект запрашивает приемник дальнейших действий.|  
|[CComControl::MessageBox](#messagebox)|Этот метод используется для создания, отображения и работы окно сообщения.|  
  
## <a name="remarks"></a>Примечания  
 `CComControl`— Это набор вспомогательных функций управления полезные и важные данные членов для элементов управления ATL. При создании стандартного элемента управления или элемент управления DHTML, используя мастер элементов управления ATL, мастер будет автоматически класс является производным от `CComControl`. `CComControl`Большинство методов из производного [CComControlBase](../../atl/reference/ccomcontrolbase-class.md).  
  
 Дополнительные сведения о создании элемента управления в разделе [учебник по ATL](../../atl/active-template-library-atl-tutorial.md). Дополнительные сведения о мастере проекта ATL см. в статье [создается проект ATL](../../atl/reference/creating-an-atl-project.md).  
  
 В демонстрации `CComControl` методы и члены данных в разделе [Кр](../../visual-cpp-samples.md) образца.  
  
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
 Вызовы [CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase) конструктор, передавая `m_hWnd` унаследованные члены данных [CWindowImpl](../../atl/reference/cwindowimpl-class.md).  
  
##  <a name="controlqueryinterface"></a>CComControl::ControlQueryInterface  
 Извлекает указатель на запрошенный интерфейс.  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID запрашиваемого интерфейса.  
  
 `ppv`  
 [out] Указатель на указатель интерфейса, идентифицируемый `iid`, или **NULL** Если интерфейс не найден.  
  
### <a name="remarks"></a>Примечания  
 Обрабатывает интерфейсы только в таблицу сопоставлений COM.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM&#15;](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]  
  
##  <a name="createcontrolwindow"></a>CComControl::CreateControlWindow  
 По умолчанию создает окно для элемента управления путем вызова `CWindowImpl::Create`.  
  
```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 [in] Дескриптор окна родительского или владельца. Должен быть указан действительный дескриптор окна. Окно управления сводится к области родительского окна.  
  
 `rcPos`  
 [in] Начальный размер и положение окна должен быть создан.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, если вы хотите сделать что-то отличного от создания одного окна, например, чтобы создать два окна, один из которых становится инструментов для элемента управления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM №&16;](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]  
  
##  <a name="fireonchanged"></a>CComControl::FireOnChanged  
 Уведомляет контейнера приемник измененного свойства элемента управления.  
  
```
HRESULT FireOnChanged(DISPID dispID);
```  
  
### <a name="parameters"></a>Параметры  
 *Идентификатор dispID*  
 [in] Идентификатор измененного свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Класса элемента управления, производного от [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638), этот метод вызывает метод [CFirePropNotifyEvent::FireOnChanged](cfirepropnotifyevent-class.md#fireonchanged) для уведомления всех подключенных `IPropertyNotifySink` интерфейсы, которые изменилось значение свойства указанного элемента управления. Если ваш класс элемента управления является производным от `IPropertyNotifySink`, этот метод возвращает `S_OK`. 
  
 Этот метод можно вызвать, даже если элемент управления не поддерживает точки подключения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM&17;](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]  
  
##  <a name="fireonrequestedit"></a>CComControl::FireOnRequestEdit  
 Уведомляет приемника контейнера, что свойства элемента управления будет изменен и что объект запрашивает приемник дальнейших действий.  
  
```
HRESULT FireOnRequestEdit(DISPID dispID);
```  
  
### <a name="parameters"></a>Параметры  
 *Идентификатор dispID*  
 [in] Идентификатор свойства будет изменен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Класса элемента управления, производного от [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638), этот метод вызывает метод [CFirePropNotifyEvent::FireOnRequestEdit](cfirepropnotifyevent-class.md#fireonrequestedit) для уведомления всех подключенных `IPropertyNotifySink` интерфейсы, свойства указанного элемента управления будет изменена. Если ваш класс элемента управления является производным от `IPropertyNotifySink`, этот метод возвращает `S_OK`.  

  
 Этот метод можно вызвать, даже если элемент управления не поддерживает точки подключения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM&18;](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]  
  
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
 Указывает содержимое и поведение диалогового окна. В разделе [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) запись в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] документации для получения списка доступных окон различных сообщений. Значение по умолчанию предоставляет простой **ОК** кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает целочисленное значение, указав одно из значений пунктов меню, перечисленных в разделе [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] документации.  
  
### <a name="remarks"></a>Примечания  
 `MessageBox`полезна как во время разработки, так и с легкостью для отображения пользователю ошибку или предупреждение.  
  
## <a name="see-also"></a>См. также  
 [Класс CWindowImpl](../../atl/reference/cwindowimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CComControlBase](../../atl/reference/ccomcontrolbase-class.md)   
 [Класс CComCompositeControl](../../atl/reference/ccomcompositecontrol-class.md)

