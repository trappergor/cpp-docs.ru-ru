---
title: "Класс CComCompositeControl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCompositeControl
- ATLCTL/ATL::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::AdviseSinkMap
- ATLCTL/ATL::CComCompositeControl::CalcExtent
- ATLCTL/ATL::CComCompositeControl::Create
- ATLCTL/ATL::CComCompositeControl::CreateControlWindow
- ATLCTL/ATL::CComCompositeControl::SetBackgroundColorFromAmbient
- ATLCTL/ATL::CComCompositeControl::m_hbrBackground
- ATLCTL/ATL::CComCompositeControl::m_hWndFocus
dev_langs:
- C++
helpviewer_keywords:
- CComCompositeControl class
- composite controls, CComCompositeControl class
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2308c2c8da67a7d6fe048f3e498e6d7ba1e3cad6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccomcompositecontrol-class"></a>Класс CComCompositeControl
Этот класс предоставляет методы, необходимые для реализации составного элемента управления.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class CComCompositeControl : public CComControl<T,CAxDialogImpl<T>>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), как хорошо от любых других интерфейсов, которые требуется поддерживать для составного элемента управления.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComCompositeControl::CComCompositeControl](#ccomcompositecontrol)|Конструктор.|  
|[CComCompositeControl:: ~ CComCompositeControl](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComCompositeControl::AdviseSinkMap](#advisesinkmap)|Этот метод используется для соединения или разъединения всех элементов управления, размещаемым составного элемента управления.|  
|[CComCompositeControl::CalcExtent](#calcextent)|Этот метод вызывается для расчета размера в **HIMETRIC** единицы ресурса диалогового окна, используемого для размещения составного элемента управления.|  
|[CComCompositeControl::Create](#create)|Этот метод вызывается для создания окна элемента управления для составного элемента управления.|  
|[CComCompositeControl::CreateControlWindow](#createcontrolwindow)|Этот метод используется для создания окна элемента управления и уведомить любой размещенного элемента управления.|  
|[CComCompositeControl::SetBackgroundColorFromAmbient](#setbackgroundcolorfromambient)|Вызовите этот метод, чтобы задать цвет фона составного элемента управления, используя цвет фона для контейнера.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComCompositeControl::m_hbrBackground](#m_hbrbackground)|Кисть фона.|  
|[CComCompositeControl::m_hWndFocus](#m_hwndfocus)|Дескриптор окна, которое в данный момент имеет фокус.|  
  
## <a name="remarks"></a>Примечания  
 Классы, производные от класса `CComCompositeControl` наследовать функциональность составного элемента управления ActiveX. Элементы управления ActiveX, производный от `CComCompositeControl` размещенных стандартное диалоговое окно. Следующие типы элементов управления, называются составные элементы управления, так как они имеют возможность размещения других элементов управления (собственные элементы управления Windows и элементы управления ActiveX).  
  
 `CComCompositeControl`идентифицирует ресурс диалогового окна для создания составного элемента управления путем просмотра для элемента данных перечисления в дочернем классе. Прямой Международной этого класса дочернего элемента присваивается идентификатор ресурса для ресурса диалогового окна, который будет использоваться в качестве окна элемента управления. Ниже приведен пример элемента данных, класс, производный от `CComCompositeControl` должен содержать для идентификации ресурса диалогового окна для окна элемента управления:  
  
 [!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]  
  
> [!NOTE]
>  Составные элементы управления являются всегда оконные, несмотря на то, что они могут содержать элементы управления без окон.  
  
 Элемент управления, реализуемый `CComCompositeControl`-производный класс содержит встроенные поведение переключения по умолчанию. Если элемент управления получает фокус, выполняется с вкладками для содержащего приложения, последовательно нажать клавишу TAB вызовет фокус циклически проходить через все вложенные элементы управления составного элемента управления, а затем из составного элемента управления и на следующий элемент в порядок вкладок контейнера. Последовательности табуляции элементов управления размещенной определяется ресурса диалогового окна, а также определяет порядок возникнет в какой переходов.  
  
> [!NOTE]
>  В порядке для сочетания клавиш для работы с `CComCompositeControl`, необходимо загрузить таблицу сочетаний клавиш, как создается элемент управления, передайте дескриптор и количество акселераторы обратно в [IOleControlImpl::GetControlInfo](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo), и Наконец уничтожить таблицы при отпускании элемента управления.  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 [CComControl](../../atl/reference/ccomcontrol-class.md)  
  
 `CComCompositeControl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="advisesinkmap"></a>CComCompositeControl::AdviseSinkMap  
 Этот метод используется для соединения или разъединения всех элементов управления, размещаемым составного элемента управления.  
  
```
HRESULT AdviseSinkMap(bool bAdvise);
```  
  
### <a name="parameters"></a>Параметры  
 `bAdvise`  
 Значение true, если все элементы управления должны быть проигнорирована; в противном случае — значение false.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`  
 Все элементы управления в событии приемником сопоставления были подключением и отключением от их источника события, успешно.  
  
 **E_FAIL**  
 Не все элементы управления в событии приемником сопоставления может быть подключен или успешно отключен от их источника события.  
  
 `E_POINTER`  
 Эта ошибка обычно означает проблему с записью в схеме приемника событий для элемента управления или проблема с аргумент шаблона, используемый в `IDispEventImpl` или `IDispEventSimpleImpl` базового класса.  
  
 **CONNECT_E_ADVISELIMIT**  
 Точка подключения уже был достигнут предел числа подключений и не может принять дополнительные.  
  
 **CONNECT_E_CANNOTCONNECT**  
 Приемник не поддерживает интерфейс, необходимый для этой точки подключения.  
  
 **CONNECT_E_NOCONNECTION**  
 Значение файла cookie не представляет допустимое соединение. Эта ошибка обычно означает проблему с записью в схеме приемника событий для элемента управления или проблема с аргумент шаблона, используемый в `IDispEventImpl` или `IDispEventSimpleImpl` базового класса.  
  
### <a name="remarks"></a>Примечания  
 Базовую реализацию этого метода поиска записей событий приемником сопоставления. Затем будет указано, или unadvises точек подключения COM-объекты, описываемого записей приемник карты приемника событий. Этот метод члена также использует тот факт, что производный класс наследует от одного экземпляра `IDispEventImpl` для каждого элемента управления в схеме приемника, который должен быть желательно или unadvised.  
  
##  <a name="calcextent"></a>CComCompositeControl::CalcExtent  
 Этот метод вызывается для расчета размера в **HIMETRIC** единицы ресурса диалогового окна, используемого для размещения составного элемента управления.  
  
```
BOOL CalcExtent(SIZE& size);
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Ссылку на **размер** структура заполняется с помощью данного метода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если элемент управления размещен на диалоговое окно. в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Возвращенный размер в `size` параметра.  
  
##  <a name="create"></a>CComCompositeControl::Create  
 Этот метод вызывается для создания окна элемента управления для составного элемента управления.  
  
```
HWND Create(
    HWND hWndParent,
    RECT& /* rcPos */,
    LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 Дескриптор родительского окна элемента управления.  
  
 `rcPos`  
 Зарезервировано.  
  
 `dwInitParam`  
 Данные, которые должны передаваться элементу управления во время создания элемента управления. Данные, передаваемые как `dwInitParam` будет показываться как **LPARAM** параметр [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) сообщение, которое будет отправляться в составного элемента управления, когда он получает создается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор в диалоговое окно только что созданный составного элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод обычно вызывается в процессе активации на месте элемента управления.  
  
##  <a name="ccomcompositecontrol"></a>CComCompositeControl::CComCompositeControl  
 Конструктор.  
  
```
CComCompositeControl();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует [CComCompositeControl::m_hbrBackground](#m_hbrbackground) и [CComCompositeControl::m_hWndFocus](#m_hwndfocus) члены данных в значение NULL.  
  
##  <a name="dtor"></a>CComCompositeControl:: ~ CComCompositeControl  
 Деструктор  
  
```
~CComCompositeControl();
```  
  
### <a name="remarks"></a>Примечания  
 Удаляет объект фон, если он существует.  
  
##  <a name="createcontrolwindow"></a>CComCompositeControl::CreateControlWindow  
 Этот метод используется для создания окна элемента управления и уведомить всех размещенных элементов управления.  
  
```
virtual HWND CreateControlWindow(
    HWND hWndParent,
    RECT& rcPos);
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 Дескриптор родительского окна элемента управления.  
  
 `rcPos`  
 Прямоугольник позиции составного элемента управления в клиентских координатах относительно `hWndParent`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор в диалоговое окно только что созданный составного элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [CComCompositeControl::Create](#create) и [CComCompositeControl::AdviseSinkMap](#advisesinkmap).  
  
##  <a name="m_hbrbackground"></a>CComCompositeControl::m_hbrBackground  
 Кисть фона.  
  
```
HBRUSH m_hbrBackground;
```  
  
##  <a name="m_hwndfocus"></a>CComCompositeControl::m_hWndFocus  
 Дескриптор окна, которое в данный момент имеет фокус.  
  
```
HWND m_hWndFocus;
```  
  
##  <a name="setbackgroundcolorfromambient"></a>CComCompositeControl::SetBackgroundColorFromAmbient  
 Вызовите этот метод, чтобы задать цвет фона составного элемента управления, используя цвет фона для контейнера.  
  
```
HRESULT SetBackgroundColorFromAmbient();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Принципы работы составного элемента управления](../../atl/atl-composite-control-fundamentals.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
