---
title: "Класс CD2DRadialGradientBrush | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::Attach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Create
- AFXRENDERTARGET/CD2DRadialGradientBrush::Destroy
- AFXRENDERTARGET/CD2DRadialGradientBrush::Detach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Get
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_pRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_RadialGradientBrushProperties
dev_langs:
- C++
helpviewer_keywords:
- CD2DRadialGradientBrush class
ms.assetid: 6c76d84a-d831-4ee2-96f1-82c1f5b0d6a9
caps.latest.revision: 17
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
ms.openlocfilehash: 8b3fd7f468745567969ba1f7e9d6871a9060582b
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dradialgradientbrush-class"></a>Класс CD2DRadialGradientBrush
Программа-оболочка для ID2D1RadialGradientBrush.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DRadialGradientBrush : public CD2DGradientBrush;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::CD2DRadialGradientBrush](#cd2dradialgradientbrush)|Создает объект CD2DLinearGradientBrush.|  
|[CD2DRadialGradientBrush:: ~ CD2DRadialGradientBrush](#_dtorcd2dradialgradientbrush)|Деструктор Вызывается при уничтожении объекта D2D кисть радиального градиента.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::Attach](#attach)|Присоединение существующих ресурсов интерфейса в объект|  
|[CD2DRadialGradientBrush::CREATE](#create)|Создает CD2DRadialGradientBrush. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DRadialGradientBrush::destroy](#destroy)|Уничтожает объект CD2DRadialGradientBrush. (Переопределяет [CD2DGradientBrush::Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|  
|[CD2DRadialGradientBrush::Detach](#detach)|Отсоединяет интерфейс ресурса из объекта|  
|[CD2DRadialGradientBrush::Get](#get)|Возвращает интерфейс ID2D1RadialGradientBrush|  
|[CD2DRadialGradientBrush::GetCenter](#getcenter)|Получает центр градиента эллипса|  
|[CD2DRadialGradientBrush::GetGradientOriginOffset](#getgradientoriginoffset)|Получает смещение начала градиента относительно центра градиента эллипса|  
|[CD2DRadialGradientBrush::GetRadiusX](#getradiusx)|Возвращает x радиус эллипса градиента|  
|[CD2DRadialGradientBrush::GetRadiusY](#getradiusy)|Получает y радиус эллипса градиента|  
|[CD2DRadialGradientBrush::SetCenter](#setcenter)|Указывает центр градиента эллипса в пространстве координат кисти|  
|[CD2DRadialGradientBrush::SetGradientOriginOffset](#setgradientoriginoffset)|Задает смещение начала градиента относительно центра градиента эллипса|  
|[CD2DRadialGradientBrush::SetRadiusX](#setradiusx)|Указывает x радиус градиента эллипс в пространстве координат кисти|  
|[CD2DRadialGradientBrush::SetRadiusY](#setradiusy)|Указывает y радиус градиента эллипс в пространстве координат кисти|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::operator ID2D1RadialGradientBrush *](#operator_id2d1radialgradientbrush_star)|Возвращает интерфейс ID2D1RadialGradientBrush|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::m_pRadialGradientBrush](#m_pradialgradientbrush)|Указатель на ID2D1RadialGradientBrush.|  
|[CD2DRadialGradientBrush::m_RadialGradientBrushProperties](#m_radialgradientbrushproperties)|Центр, смещение начала градиента и x radius и y радиус кисти градиента.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)  
  
 `CD2DRadialGradientBrush`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="_dtorcd2dradialgradientbrush"></a>CD2DRadialGradientBrush:: ~ CD2DRadialGradientBrush  
 Деструктор Вызывается при уничтожении объекта D2D кисть радиального градиента.  
  
```  
virtual ~CD2DRadialGradientBrush();
```  
  
##  <a name="attach"></a>CD2DRadialGradientBrush::Attach  
 Присоединение существующих ресурсов интерфейса в объект  
  
```  
void Attach(ID2D1RadialGradientBrush* pResource);
```  
  
### <a name="parameters"></a>Параметры  
 `pResource`  
 Существующий интерфейс ресурсов. Не может иметь значение NULL  
  
##  <a name="cd2dradialgradientbrush"></a>CD2DRadialGradientBrush::CD2DRadialGradientBrush  
 Создает объект CD2DLinearGradientBrush.  
  
```  
CD2DRadialGradientBrush(
    CRenderTarget* pParentTarget,  
    const D2D1_GRADIENT_STOP* gradientStops,  
    UINT gradientStopsCount,  
    D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES RadialGradientBrushProperties,  
    D2D1_GAMMA colorInterpolationGamma = D2D1_GAMMA_2_2,  
    D2D1_EXTEND_MODE extendMode = D2D1_EXTEND_MODE_CLAMP,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentTarget`  
 Указатель на целевой объект отрисовки.  
  
 `gradientStops`  
 Указатель на массив структур D2D1_GRADIENT_STOP.  
  
 `gradientStopsCount`  
 Значение больше или равно 1, указывающее число ступеней градиента в массиве gradientStops.  
  
 `RadialGradientBrushProperties`  
 Центр, смещение начала градиента и x radius и y радиус кисти градиента.  
  
 `colorInterpolationGamma`  
 Пространство, в какой цвет выполняется интерполяции между позициями градиента.  
  
 `extendMode`  
 Поведение градиента за пределами нормализованных диапазон [0,1].  
  
 `pBrushProperties`  
 Указатель непрозрачности и преобразование кисти.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельцем (pParentTarget).  
  
##  <a name="create"></a>CD2DRadialGradientBrush::CREATE  
 Создает CD2DRadialGradientBrush.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pRenderTarget`  
 Указатель на целевой объект отрисовки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. В противном случае — возвращает код ошибки HRESULT.  
  
##  <a name="destroy"></a>CD2DRadialGradientBrush::destroy  
 Уничтожает объект CD2DRadialGradientBrush.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DRadialGradientBrush::Detach  
 Отсоединяет интерфейс ресурса из объекта  
  
```  
ID2D1RadialGradientBrush* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс отсоединенных ресурсов.  
  
##  <a name="get"></a>CD2DRadialGradientBrush::Get  
 Возвращает интерфейс ID2D1RadialGradientBrush  
  
```  
ID2D1RadialGradientBrush* Get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1RadialGradientBrush или значение NULL, если объект еще не инициализирован.  
  
##  <a name="getcenter"></a>CD2DRadialGradientBrush::GetCenter  
 Получает центр градиента эллипса  
  
```  
CD2DPointF GetCenter() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Центр градиента эллипса. Это значение выражается в пространстве координат кисти  
  
##  <a name="getgradientoriginoffset"></a>CD2DRadialGradientBrush::GetGradientOriginOffset  
 Получает смещение начала градиента относительно центра градиента эллипса  
  
```  
CD2DPointF GetGradientOriginOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Смещение начала градиента в центре градиента эллипса. Это значение выражается в пространстве координат кисти  
  
##  <a name="getradiusx"></a>CD2DRadialGradientBrush::GetRadiusX  
 Возвращает x радиус эллипса градиента  
  
```  
FLOAT GetRadiusX() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 X радиус эллипса градиента. Это значение выражается в пространстве координат кисти  
  
##  <a name="getradiusy"></a>CD2DRadialGradientBrush::GetRadiusY  
 Получает y радиус эллипса градиента  
  
```  
FLOAT GetRadiusY() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Y радиус эллипса градиента. Это значение выражается в пространстве координат кисти  
  
##  <a name="m_pradialgradientbrush"></a>CD2DRadialGradientBrush::m_pRadialGradientBrush  
 Указатель на ID2D1RadialGradientBrush.  
  
```  
ID2D1RadialGradientBrush* m_pRadialGradientBrush;  
```  
  
##  <a name="m_radialgradientbrushproperties"></a>CD2DRadialGradientBrush::m_RadialGradientBrushProperties  
 Центр, смещение начала градиента и x radius и y радиус кисти градиента.  
  
```  
D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES m_RadialGradientBrushProperties;  
```  
  
##  <a name="operator_id2d1radialgradientbrush_star"></a>CD2DRadialGradientBrush::operator ID2D1RadialGradientBrush *  
 Возвращает интерфейс ID2D1RadialGradientBrush  
  
```  
operator ID2D1RadialGradientBrush*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1RadialGradientBrush или значение NULL, если объект еще не инициализирован.  
  
##  <a name="setcenter"></a>CD2DRadialGradientBrush::SetCenter  
 Указывает центр градиента эллипса в пространстве координат кисти  
  
```  
void SetCenter(CD2DPointF point);
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Центр эллипса, в пространстве координат кисти градиента  
  
##  <a name="setgradientoriginoffset"></a>CD2DRadialGradientBrush::SetGradientOriginOffset  
 Задает смещение начала градиента относительно центра градиента эллипса  
  
```  
void SetGradientOriginOffset(CD2DPointF gradientOriginOffset);
```  
  
### <a name="parameters"></a>Параметры  
 `gradientOriginOffset`  
 Смещение начала градиента в центре градиента эллипса  
  
##  <a name="setradiusx"></a>CD2DRadialGradientBrush::SetRadiusX  
 Указывает x радиус градиента эллипс в пространстве координат кисти  
  
```  
void SetRadiusX(FLOAT radiusX);
```  
  
### <a name="parameters"></a>Параметры  
 `radiusX`  
 X радиус эллипса градиента. Это значение задается в пространстве координат кисти  
  
##  <a name="setradiusy"></a>CD2DRadialGradientBrush::SetRadiusY  
 Указывает y радиус градиента эллипс в пространстве координат кисти  
  
```  
void SetRadiusY(FLOAT radiusY);
```  
  
### <a name="parameters"></a>Параметры  
 `radiusY`  
 Y радиус эллипса градиента. Это значение задается в пространстве координат кисти  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

