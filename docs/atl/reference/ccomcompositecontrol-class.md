---
title: Класс CComCompositeControl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 892cccea65b9e1b6f0c1eec21d3973e84a0fba03
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43223263"
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
 *T*  
 Ваш класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), как хорошо от любых других интерфейсов, которую требуется поддерживать для составного элемента управления.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComCompositeControl::CComCompositeControl](#ccomcompositecontrol)|Конструктор.|  
|[CComCompositeControl:: ~ CComCompositeControl](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComCompositeControl::AdviseSinkMap](#advisesinkmap)|Этот метод используется для соединения или разъединения всех элементов управления, размещаемым в составной элемент управления.|  
|[CComCompositeControl::CalcExtent](#calcextent)|Вызовите этот метод, для которого требуется вычислить размер в единицах HIMETRIC ресурса диалогового окна, используемого для размещения составного элемента управления.|  
|[CComCompositeControl::Create](#create)|Этот метод вызывается для создания окна элемента управления для составного элемента управления.|  
|[CComCompositeControl::CreateControlWindow](#createcontrolwindow)|Этот метод используется для создания окна элемента управления и уведомить любой размещенный элемент управления.|  
|[CComCompositeControl::SetBackgroundColorFromAmbient](#setbackgroundcolorfromambient)|Вызовите этот метод, чтобы задать цвет фона составного элемента управления, используя цвет фона контейнера.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComCompositeControl::m_hbrBackground](#m_hbrbackground)|Кисть фона.|  
|[CComCompositeControl::m_hWndFocus](#m_hwndfocus)|Дескриптор окна, которое в данный момент имеет фокус.|  
  
## <a name="remarks"></a>Примечания  
 Классы, производные от класса `CComCompositeControl` наследовать функциональность составного элемента управления ActiveX. Элементы управления ActiveX, производный от `CComCompositeControl` размещенных стандартное диалоговое окно. Эти типы элементов управления, называются составных элементов управления, так как они смогут размещать другие элементы (собственные элементы управления Windows и элементы управления ActiveX).  
  
 `CComCompositeControl` идентифицирует ресурс диалогового окна для использования при создании составного элемента управления путем поиска для перечислимых данных члена в дочернем классе. Элемент IDD этого дочернего класса присваивается идентификатор ресурса для ресурса диалогового окна, который будет использоваться в качестве окна элемента управления. Ниже приведен пример элемента данных, класс, производный от `CComCompositeControl` должен содержать для идентификации ресурса диалогового окна для окна элемента управления:  
  
 [!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]  
  
> [!NOTE]
>  Составные элементы управления всегда являются оконными элементами управления, несмотря на то, что они могут содержать элементы управления без окон.  
  
 Элемент управления, реализованный `CComCompositeControl`-производный класс обладает встроенными поведение перехода по умолчанию. Когда элемент управления получает фокус по чтобы добавляются на вкладки приложения-контейнера, можно последовательно нажимать клавишу TAB вызовет фокус циклически проходить через все вложенные элементы управления составного элемента управления, а затем из составного элемента управления и к следующему элементу в последовательность перехода объекта контейнера. Последовательности табуляции элементов управления размещенной определяется ресурса диалогового окна и определяет порядок, в какие переходы будут происходить.  
  
> [!NOTE]
>  В порядке для ускорителей для нормальной работы `CComCompositeControl`, необходимо загрузить в таблицу сочетаний клавиш, как создается элемент управления, передайте дескриптор и номер ускорителей обратно в [IOleControlImpl::GetControlInfo](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo), и Наконец уничтожить таблицы, при выпуске элемента управления.  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 [CComControl](../../atl/reference/ccomcontrol-class.md)  
  
 `CComCompositeControl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="advisesinkmap"></a>  CComCompositeControl::AdviseSinkMap  
 Этот метод используется для соединения или разъединения всех элементов управления, размещаемым в составной элемент управления.  
  
```
HRESULT AdviseSinkMap(bool bAdvise);
```  
  
### <a name="parameters"></a>Параметры  
 *bAdvise*  
 Значение true, если все элементы управления, которому необходимо предоставить рекомендацию; в противном случае — false.  
  
### <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Все элементы управления в случае приемника карты были подключены или успешно отключен от их источника события.  
  
 E_FAIL  
 Не все элементы управления в событии приемника карты может быть подключен или успешно отключен от их источника события.  
  
 E_POINTER  
 Эта ошибка обычно указывает на проблему с записью в сопоставлении приемника событий элемента управления или неполадки аргумент шаблона, используемый в `IDispEventImpl` или `IDispEventSimpleImpl` базового класса.  
  
 CONNECT_E_ADVISELIMIT  
 Точка подключения уже достигнут лимит подключений и не может принимать любое другое.  
  
 CONNECT_E_CANNOTCONNECT  
 Приемник не поддерживает интерфейс, необходимый для этой точки подключения.  
  
 CONNECT_E_NOCONNECTION  
 Значение файла cookie не представляет допустимое соединение. Эта ошибка обычно указывает на проблему с записью в сопоставлении приемника событий элемента управления или неполадки аргумент шаблона, используемый в `IDispEventImpl` или `IDispEventSimpleImpl` базового класса.  
  
### <a name="remarks"></a>Примечания  
 Базовую реализацию этого метода выполняет поиск по записи событий приемника карты. Затем будет указано, или не рекомендуйте точки подключения COM-объекты, описываемого записей приемника карты приемника событий. Такой метод члена также основывается на тот факт, что производный класс наследует от одного экземпляра `IDispEventImpl` для каждого элемента управления в карте приемника, желательно или негативной рекомендации.  
  
##  <a name="calcextent"></a>  CComCompositeControl::CalcExtent  
 Вызовите этот метод, для которого требуется вычислить размер в единицах HIMETRIC ресурса диалогового окна, используемого для размещения составного элемента управления.  
  
```
BOOL CalcExtent(SIZE& size);
```  
  
### <a name="parameters"></a>Параметры  
 *size*  
 Ссылку на `SIZE` структура заполняется с помощью данного метода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если элемент управления размещен в диалоговом окне; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Возвращенный размер в *размер* параметра.  
  
##  <a name="create"></a>  CComCompositeControl::Create  
 Этот метод вызывается для создания окна элемента управления для составного элемента управления.  
  
```
HWND Create(
    HWND hWndParent,
    RECT& /* rcPos */,
    LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *hWndParent*  
 Дескриптор родительского окна элемента управления.  
  
 *rcPos*  
 Зарезервировано.  
  
 *dwInitParam*  
 Данные должны передаваться элементу управления во время создания элемента управления. Данные, передаваемые как *dwInitParam* будут отображаться как параметр LPARAM [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog) сообщения, которое будет отправляться в составной элемент управления, он будет создан.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор диалоговом окне только что созданный составного элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод обычно вызывается во время активации элемента управления.  
  
##  <a name="ccomcompositecontrol"></a>  CComCompositeControl::CComCompositeControl  
 Конструктор.  
  
```
CComCompositeControl();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует [CComCompositeControl::m_hbrBackground](#m_hbrbackground) и [CComCompositeControl::m_hWndFocus](#m_hwndfocus) данные-члены в значение NULL.  
  
##  <a name="dtor"></a>  CComCompositeControl:: ~ CComCompositeControl  
 Деструктор  
  
```
~CComCompositeControl();
```  
  
### <a name="remarks"></a>Примечания  
 Удаляет объект фон, если он существует.  
  
##  <a name="createcontrolwindow"></a>  CComCompositeControl::CreateControlWindow  
 Этот метод используется для создания окна элемента управления и уведомить всех размещенных элементов управления.  
  
```
virtual HWND CreateControlWindow(
    HWND hWndParent,
    RECT& rcPos);
```  
  
### <a name="parameters"></a>Параметры  
 *hWndParent*  
 Дескриптор родительского окна элемента управления.  
  
 *rcPos*  
 Прямоугольник позиции составного элемента управления в клиенте координаты относительно *hWndParent*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор в диалоговое окно только что созданный составного элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [CComCompositeControl::Create](#create) и [CComCompositeControl::AdviseSinkMap](#advisesinkmap).  
  
##  <a name="m_hbrbackground"></a>  CComCompositeControl::m_hbrBackground  
 Кисть фона.  
  
```
HBRUSH m_hbrBackground;
```  
  
##  <a name="m_hwndfocus"></a>  CComCompositeControl::m_hWndFocus  
 Дескриптор окна, которое в данный момент имеет фокус.  
  
```
HWND m_hWndFocus;
```  
  
##  <a name="setbackgroundcolorfromambient"></a>  CComCompositeControl::SetBackgroundColorFromAmbient  
 Вызовите этот метод, чтобы задать цвет фона составного элемента управления, используя цвет фона контейнера.  
  
```
HRESULT SetBackgroundColorFromAmbient();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Основы составного элемента управления](../../atl/atl-composite-control-fundamentals.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
