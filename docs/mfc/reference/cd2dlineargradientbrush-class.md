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
- CD2DLinearGradientBrush [MFC], CD2DLinearGradientBrush
- CD2DLinearGradientBrush [MFC], Attach
- CD2DLinearGradientBrush [MFC], Create
- CD2DLinearGradientBrush [MFC], Destroy
- CD2DLinearGradientBrush [MFC], Detach
- CD2DLinearGradientBrush [MFC], Get
- CD2DLinearGradientBrush [MFC], GetEndPoint
- CD2DLinearGradientBrush [MFC], GetStartPoint
- CD2DLinearGradientBrush [MFC], SetEndPoint
- CD2DLinearGradientBrush [MFC], SetStartPoint
- CD2DLinearGradientBrush [MFC], m_LinearGradientBrushProperties
- CD2DLinearGradientBrush [MFC], m_pLinearGradientBrush
ms.assetid: d4be9ff9-0ea8-45e6-9b8d-f3bc5673cbac
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 19c060c846d8dfd12a8b783f0b01153c9a424cfe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cd2dlineargradientbrush-class"></a>Класс CD2DLinearGradientBrush
Программа-оболочка для ID2D1LinearGradientBrush.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DLinearGradientBrush : public CD2DGradientBrush;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::CD2DLinearGradientBrush](#cd2dlineargradientbrush)|Создает объект CD2DLinearGradientBrush.|  
|[CD2DLinearGradientBrush:: ~ CD2DLinearGradientBrush](#_dtorcd2dlineargradientbrush)|Деструктор Вызывается при уничтожении объекта D2D кисти линейного градиента.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::Attach](#attach)|Присоединяет существующий ресурс интерфейс для объекта|  
|[CD2DLinearGradientBrush::CREATE](#create)|Создает CD2DLinearGradientBrush. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DLinearGradientBrush::destroy](#destroy)|Уничтожает объект CD2DLinearGradientBrush. (Переопределяет [CD2DGradientBrush::Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|  
|[CD2DLinearGradientBrush::Detach](#detach)|Отсоединяет интерфейса ресурсов из объекта|  
|[CD2DLinearGradientBrush::Get](#get)|Возвращает интерфейс ID2D1LinearGradientBrush|  
|[CD2DLinearGradientBrush::GetEndPoint](#getendpoint)|Получает конечные координаты для линейного градиента|  
|[CD2DLinearGradientBrush::GetStartPoint](#getstartpoint)|Извлекает начальные координаты для линейного градиента|  
|[CD2DLinearGradientBrush::SetEndPoint](#setendpoint)|Задает конечные координаты для линейного градиента в координатной системе кисти|  
|[CD2DLinearGradientBrush::SetStartPoint](#setstartpoint)|Задает начальные координаты для линейного градиента в координатной системе кисти|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::operator ID2D1LinearGradientBrush *](#operator_id2d1lineargradientbrush_star)|Возвращает интерфейс ID2D1LinearGradientBrush|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
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
 Присоединяет существующий ресурс интерфейс для объекта  
  
```  
void Attach(ID2D1LinearGradientBrush* pResource);
```  
  
### <a name="parameters"></a>Параметры  
 `pResource`  
 Интерфейс существующего ресурса. Не может иметь значение NULL  
  
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
 Значение больше или равно 1, указывающее количество градиента в массиве gradientStops.  
  
 `LinearGradientBrushProperties`  
 Начальная и конечная точки градиента.  
  
 `colorInterpolationGamma`  
 Место на диске, в какой цвет выполняется интерполяцию между позиции градиента.  
  
 `extendMode`  
 Поведение вне диапазона [0,1] нормализованный градиента.  
  
 `pBrushProperties`  
 Указатель непрозрачности и преобразования кисти.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельца (pParentTarget).  
  
##  <a name="create"></a>CD2DLinearGradientBrush::CREATE  
 Создает CD2DLinearGradientBrush.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pRenderTarget`  
 Указатель на целевой объект отрисовки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. В противном случае возвращается код ошибки HRESULT.  
  
##  <a name="destroy"></a>CD2DLinearGradientBrush::destroy  
 Уничтожает объект CD2DLinearGradientBrush.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DLinearGradientBrush::Detach  
 Отсоединяет интерфейса ресурсов из объекта  
  
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
 Получает конечные координаты для линейного градиента  
  
```  
CD2DPointF GetEndPoint() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Конечные двумерные координаты для линейного градиента в координатной системе кисти  
  
##  <a name="getstartpoint"></a>CD2DLinearGradientBrush::GetStartPoint  
 Извлекает начальные координаты для линейного градиента  
  
```  
CD2DPointF GetStartPoint() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Начальные двумерные координаты для линейного градиента в координатной системе кисти  
  
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
 Задает конечные координаты для линейного градиента в координатной системе кисти  
  
```  
void SetEndPoint(CD2DPointF point);
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Конечные двумерные координаты для линейного градиента в координатной системе кисти  
  
##  <a name="setstartpoint"></a>CD2DLinearGradientBrush::SetStartPoint  
 Задает начальные координаты для линейного градиента в координатной системе кисти  
  
```  
void SetStartPoint(CD2DPointF point);
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Начальные двумерные координаты для линейного градиента в координатной системе кисти  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
