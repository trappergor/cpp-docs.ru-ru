---
title: "Класс CD2DLinearGradientBrush | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::Attach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Create
- AFXRENDERTARGET/CD2DLinearGradientBrush::Destroy
- AFXRENDERTARGET/CD2DLinearGradientBrush::Detach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Get
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_LinearGradientBrushProperties
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_pLinearGradientBrush
dev_langs:
- C++
helpviewer_keywords:
- CD2DLinearGradientBrush class
ms.assetid: d4be9ff9-0ea8-45e6-9b8d-f3bc5673cbac
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: dd288478a751d921cc4d9fcd9433e391275cee66
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dlineargradientbrush-class"></a>Класс CD2DLinearGradientBrush
Программа-оболочка для ID2D1LinearGradientBrush.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DLinearGradientBrush : public CD2DGradientBrush;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::CD2DLinearGradientBrush](#cd2dlineargradientbrush)|Создает объект CD2DLinearGradientBrush.|  
|[CD2DLinearGradientBrush:: ~ CD2DLinearGradientBrush](#_dtorcd2dlineargradientbrush)|Деструктор Вызывается при уничтожении объекта D2D кисти линейного градиента.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::Attach](#attach)|Присоединение существующих ресурсов интерфейса в объект|  
|[CD2DLinearGradientBrush::CREATE](#create)|Создает CD2DLinearGradientBrush. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DLinearGradientBrush::destroy](#destroy)|Уничтожает объект CD2DLinearGradientBrush. (Переопределяет [CD2DGradientBrush::Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|  
|[CD2DLinearGradientBrush::Detach](#detach)|Отсоединяет интерфейс ресурса из объекта|  
|[CD2DLinearGradientBrush::Get](#get)|Возвращает интерфейс ID2D1LinearGradientBrush|  
|[CD2DLinearGradientBrush::GetEndPoint](#getendpoint)|Получает конечные координаты линейного градиента|  
|[CD2DLinearGradientBrush::GetStartPoint](#getstartpoint)|Получает начальные координаты линейного градиента|  
|[CD2DLinearGradientBrush::SetEndPoint](#setendpoint)|Задает конечные координаты в пространстве координат кисти линейного градиента|  
|[CD2DLinearGradientBrush::SetStartPoint](#setstartpoint)|Задает начальные координаты в пространстве координат кисти линейного градиента|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::operator ID2D1LinearGradientBrush *](#operator_id2d1lineargradientbrush_star)|Возвращает интерфейс ID2D1LinearGradientBrush|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::m_LinearGradientBrushProperties](#m_lineargradientbrushproperties)|Начальная и конечная точки градиента.|  
|[CD2DLinearGradientBrush::m_pLinearGradientBrush](#m_plineargradientbrush)|Указатель на ID2D1LinearGradientBrush.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)  
  
 `CD2DLinearGradientBrush`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="_dtorcd2dlineargradientbrush"></a>CD2DLinearGradientBrush:: ~ CD2DLinearGradientBrush  
 Деструктор Вызывается при уничтожении объекта D2D кисти линейного градиента.  
  
```  
virtual ~CD2DLinearGradientBrush();
```  
  
##  <a name="attach"></a>CD2DLinearGradientBrush::Attach  
 Присоединение существующих ресурсов интерфейса в объект  
  
```  
void Attach(ID2D1LinearGradientBrush* pResource);
```  
  
### <a name="parameters"></a>Параметры  
 `pResource`  
 Существующий интерфейс ресурсов. Не может иметь значение NULL  
  
##  <a name="cd2dlineargradientbrush"></a>CD2DLinearGradientBrush::CD2DLinearGradientBrush  
 Создает объект CD2DLinearGradientBrush.  
  
```  
CD2DLinearGradientBrush(
    CRenderTarget* pParentTarget,  
    const D2D1_GRADIENT_STOP* gradientStops,  
    UINT gradientStopsCount,  
    D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES LinearGradientBrushProperties,  
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
  
 `LinearGradientBrushProperties`  
 Начальная и конечная точки градиента.  
  
 `colorInterpolationGamma`  
 Пространство, в какой цвет выполняется интерполяция между позициями градиента.  
  
 `extendMode`  
 Поведение градиента за пределами нормализованных диапазон [0,1].  
  
 `pBrushProperties`  
 Указатель непрозрачности и преобразование кисти.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельцем (pParentTarget).  
  
##  <a name="create"></a>CD2DLinearGradientBrush::CREATE  
 Создает CD2DLinearGradientBrush.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pRenderTarget`  
 Указатель на целевой объект отрисовки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. В противном случае — возвращает код ошибки HRESULT.  
  
##  <a name="destroy"></a>CD2DLinearGradientBrush::destroy  
 Уничтожает объект CD2DLinearGradientBrush.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DLinearGradientBrush::Detach  
 Отсоединяет интерфейс ресурса из объекта  
  
```  
ID2D1LinearGradientBrush* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс отсоединенных ресурсов.  
  
##  <a name="get"></a>CD2DLinearGradientBrush::Get  
 Возвращает интерфейс ID2D1LinearGradientBrush  
  
```  
ID2D1LinearGradientBrush* Get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1LinearGradientBrush или значение NULL, если объект еще не инициализирован.  
  
##  <a name="getendpoint"></a>CD2DLinearGradientBrush::GetEndPoint  
 Получает конечные координаты линейного градиента  
  
```  
CD2DPointF GetEndPoint() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Конечные двухмерные координаты линейного градиента в пространстве координат кисти  
  
##  <a name="getstartpoint"></a>CD2DLinearGradientBrush::GetStartPoint  
 Получает начальные координаты линейного градиента  
  
```  
CD2DPointF GetStartPoint() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Начальные двухмерные координаты линейного градиента в пространстве координат кисти  
  
##  <a name="m_lineargradientbrushproperties"></a>CD2DLinearGradientBrush::m_LinearGradientBrushProperties  
 Начальная и конечная точки градиента.  
  
```  
D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES m_LinearGradientBrushProperties;  
```  
  
##  <a name="m_plineargradientbrush"></a>CD2DLinearGradientBrush::m_pLinearGradientBrush  
 Указатель на ID2D1LinearGradientBrush.  
  
```  
ID2D1LinearGradientBrush* m_pLinearGradientBrush;  
```  
  
##  <a name="operator_id2d1lineargradientbrush_star"></a>CD2DLinearGradientBrush::operator ID2D1LinearGradientBrush *  
 Возвращает интерфейс ID2D1LinearGradientBrush  
  
```  
operator ID2D1LinearGradientBrush*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1LinearGradientBrush или значение NULL, если объект еще не инициализирован.  
  
##  <a name="setendpoint"></a>CD2DLinearGradientBrush::SetEndPoint  
 Задает конечные координаты в пространстве координат кисти линейного градиента  
  
```  
void SetEndPoint(CD2DPointF point);
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Конечные двухмерные координаты линейного градиента в пространстве координат кисти  
  
##  <a name="setstartpoint"></a>CD2DLinearGradientBrush::SetStartPoint  
 Задает начальные координаты в пространстве координат кисти линейного градиента  
  
```  
void SetStartPoint(CD2DPointF point);
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Начальные двухмерные координаты линейного градиента в пространстве координат кисти  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

