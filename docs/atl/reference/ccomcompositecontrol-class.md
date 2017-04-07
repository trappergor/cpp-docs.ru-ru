---
title: "Класс CComCompositeControl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ab99b8682e8b529cc124fbda1e6facaac48d0927
ms.lasthandoff: 02/24/2017

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
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), как от любых других интерфейсов также требуется поддержка составного элемента управления.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComCompositeControl::CComCompositeControl](#ccomcompositecontrol)|Конструктор.|  
|[CComCompositeControl:: ~ CComCompositeControl](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComCompositeControl::AdviseSinkMap](#advisesinkmap)|Этот метод используется для соединения или разъединения всех элементов управления, размещенных на составного элемента управления.|  
|[CComCompositeControl::CalcExtent](#calcextent)|Этот метод вызывается для расчета размера в **HIMETRIC** единицы ресурса диалогового окна, используемого для размещения составного элемента управления.|  
|[CComCompositeControl::Create](#create)|Этот метод вызывается для создания окна элемента управления для составного элемента управления.|  
|[CComCompositeControl::CreateControlWindow](#createcontrolwindow)|Этот метод для создания окна элемента управления и уведомить любой размещенного элемента управления.|  
|[CComCompositeControl::SetBackgroundColorFromAmbient](#setbackgroundcolorfromambient)|Вызовите этот метод, чтобы задать цвет фона для составного элемента управления, используя цвет фона контейнера.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComCompositeControl::m_hbrBackground](#m_hbrbackground)|Кисть фона.|  
|[CComCompositeControl::m_hWndFocus](#m_hwndfocus)|Дескриптор окна, которое в данный момент имеет фокус.|  
  
## <a name="remarks"></a>Примечания  
 Классы, производные от класса `CComCompositeControl` наследует функциональные возможности составного элемента управления ActiveX. Элементы управления ActiveX, производный от `CComCompositeControl` размещаемые стандартное диалоговое окно. Следующие типы элементов управления, называются составных элементов управления, так как они могут содержать другие элементы управления (собственные элементы управления Windows и элементы управления ActiveX).  
  
 `CComCompositeControl`идентифицирует ресурс диалогового окна для использования при создании составного элемента управления путем просмотра для перечислимых данных члена в дочернем классе. Идентификатор ресурса для ресурса диалогового окна, который будет использоваться в качестве окна элемента управления имеет значение члена IDD этого дочернего класса. Ниже приведен пример элемента данных, класс, производный от `CComCompositeControl` должен содержать для идентификации ресурса диалогового окна для окна элемента управления:  
  
 [!code-cpp[NVC_ATL_COM&#13;](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]  
  
> [!NOTE]
>  Составные элементы управления всегда являются элементов управления с окнами, несмотря на то, что они могут содержать элементы управления без окон.  
  
 Элемент управления, реализованный `CComCompositeControl`-производного класса имеет значение по умолчанию поведение, встроенных в переключения. Когда элемент управления получает фокус, выполняется с вкладками для содержащего приложения, последовательно нажав клавишу TAB приведет к фокус циклически проходить через все составного элемента управления содержащиеся элементы управления, затем из составного элемента управления, а затем к следующему элементу в последовательности табуляции контейнера. Последовательности табуляции элементов управления размещенной определяется ресурс диалогового окна, а также определяет порядок табуляции, который будет выполняться.  
  
> [!NOTE]
>  Чтобы ускорители для работы с `CComCompositeControl`, необходимо загрузить таблицу сочетаний клавиш, как создается элемент управления, передайте дескриптор и количество ускорителей обратно в [IOleControlImpl::GetControlInfo](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo)и наконец уничтожить таблицу при отпускании элемента управления.  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM&#14;](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 [CComControl](../../atl/reference/ccomcontrol-class.md)  
  
 `CComCompositeControl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="advisesinkmap"></a>CComCompositeControl::AdviseSinkMap  
 Этот метод используется для соединения или разъединения всех элементов управления, размещенных на составного элемента управления.  
  
```
HRESULT AdviseSinkMap(bool bAdvise);
```  
  
### <a name="parameters"></a>Параметры  
 `bAdvise`  
 Значение true, если все элементы управления знать; в противном случае — значение false.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`  
 Все элементы управления в событии приемником сопоставления были подключены или успешно отключен от их источника события.  
  
 **E_FAIL**  
 Не все элементы управления в событии приемником сопоставления может быть подключен или успешно отключен от их источника события.  
  
 `E_POINTER`  
 Эта ошибка обычно означает проблему с записи в элемент управления картой приемника событий или с помощью аргумента шаблона, используемый в `IDispEventImpl` или `IDispEventSimpleImpl` базового класса.  
  
 **CONNECT_E_ADVISELIMIT**  
 Точка подключения уже достигнут лимит подключений и не может принимать любое другое.  
  
 **CONNECT_E_CANNOTCONNECT**  
 Приемник не поддерживает интерфейс, необходимый для этой точки подключения.  
  
 **CONNECT_E_NOCONNECTION**  
 Значение файла cookie не представляет допустимое соединение. Эта ошибка обычно означает проблему с записи в элемент управления картой приемника событий или с помощью аргумента шаблона, используемый в `IDispEventImpl` или `IDispEventSimpleImpl` базового класса.  
  
### <a name="remarks"></a>Примечания  
 Базовая реализация этого метода выполняет поиск по записи событий приемника карты. Затем содержания или unadvises точек подключения COM-объекты, описываемого картой приемника событий приемника операции. Этот метод член также основывается на тот факт, что производный класс наследует от одного экземпляра `IDispEventImpl` для каждого элемента управления в схеме приемника, который должен быть желательно или unadvised.  
  
##  <a name="calcextent"></a>CComCompositeControl::CalcExtent  
 Этот метод вызывается для расчета размера в **HIMETRIC** единицы ресурса диалогового окна, используемого для размещения составного элемента управления.  
  
```
BOOL CalcExtent(SIZE& size);
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Ссылку на **размер** структура заполняется с помощью данного метода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если элемент управления размещен в диалоговом окне; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Возвращенный размер в `size` параметр.  
  
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
 Данные передаются в элемент управления во время создания элемента управления. Данные, передаваемые как `dwInitParam` будет отображаться как **LPARAM** параметр [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) сообщения, которое будет отправляться в составной элемент управления, он создается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор диалоговое окно только что созданный составного элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Обычно этот метод вызывается во время активации на месте элемента управления.  
  
##  <a name="ccomcompositecontrol"></a>CComCompositeControl::CComCompositeControl  
 Конструктор.  
  
```
CComCompositeControl();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует [CComCompositeControl::m_hbrBackground](#m_hbrbackground) и [CComCompositeControl::m_hWndFocus](#m_hwndfocus) члены данных значение NULL.  
  
##  <a name="dtor"></a>CComCompositeControl:: ~ CComCompositeControl  
 Деструктор  
  
```
~CComCompositeControl();
```  
  
### <a name="remarks"></a>Примечания  
 Удаляет объект заднего плана, если он существует.  
  
##  <a name="createcontrolwindow"></a>CComCompositeControl::CreateControlWindow  
 Этот метод для создания окна элемента управления и уведомить всех размещенных элементов управления.  
  
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
 Вызовите этот метод, чтобы задать цвет фона для составного элемента управления, используя цвет фона контейнера.  
  
```
HRESULT SetBackgroundColorFromAmbient();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Основы составного элемента управления](../../atl/atl-composite-control-fundamentals.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

