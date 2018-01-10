---
title: "Класс CD2DGradientBrush | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::Destroy
- AFXRENDERTARGET/CD2DGradientBrush::m_arGradientStops
- AFXRENDERTARGET/CD2DGradientBrush::m_colorInterpolationGamma
- AFXRENDERTARGET/CD2DGradientBrush::m_extendMode
- AFXRENDERTARGET/CD2DGradientBrush::m_pGradientStops
dev_langs: C++
helpviewer_keywords:
- CD2DGradientBrush [MFC], CD2DGradientBrush
- CD2DGradientBrush [MFC], Destroy
- CD2DGradientBrush [MFC], m_arGradientStops
- CD2DGradientBrush [MFC], m_colorInterpolationGamma
- CD2DGradientBrush [MFC], m_extendMode
- CD2DGradientBrush [MFC], m_pGradientStops
ms.assetid: 5bf133e6-16b7-4e3a-845d-0ce63fafe5ec
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c03d489b3059ddadf5783719f297371433a599e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cd2dgradientbrush-class"></a>Класс CD2DGradientBrush
Базовый класс CD2DLinearGradientBrush и CD2DRadialGradientBrush классов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DGradientBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DGradientBrush::CD2DGradientBrush](#cd2dgradientbrush)|Создает объект CD2DGradientBrush.|  
|[CD2DGradientBrush:: ~ CD2DGradientBrush](#cd2dgradientbrush__~cd2dgradientbrush)|Деструктор Вызывается при уничтожении объекта D2D градиентной кисти.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DGradientBrush::destroy](#destroy)|Уничтожает объект CD2DGradientBrush. (Переопределяет [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CD2DGradientBrush::m_arGradientStops](#m_argradientstops)|Массив структур D2D1_GRADIENT_STOP.|  
|[CD2DGradientBrush::m_colorInterpolationGamma](#m_colorinterpolationgamma)|Место на диске, в какой цвет выполняется интерполяцию между позиции градиента.|  
|[CD2DGradientBrush::m_extendMode](#m_extendmode)|Поведение вне диапазона [0,1] нормализованный градиента.|  
|[CD2DGradientBrush::m_pGradientStops](#m_pgradientstops)|Указатель на массив структур D2D1_GRADIENT_STOP.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 `CD2DGradientBrush`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="_dtorcd2dgradientbrush"></a>CD2DGradientBrush:: ~ CD2DGradientBrush  
 Деструктор Вызывается при уничтожении объекта D2D градиентной кисти.  
  
```  
virtual ~CD2DGradientBrush();
```  
  
##  <a name="cd2dgradientbrush"></a>CD2DGradientBrush::CD2DGradientBrush  
 Создает объект CD2DGradientBrush.  
  
```  
CD2DGradientBrush(
    CRenderTarget* pParentTarget,  
    const D2D1_GRADIENT_STOP* gradientStops,  
    UINT gradientStopsCount,  
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
  
 `colorInterpolationGamma`  
 Место на диске, в какой цвет выполняется интерполяцию между позиции градиента.  
  
 `extendMode`  
 Поведение вне диапазона [0,1] нормализованный градиента.  
  
 `pBrushProperties`  
 Указатель непрозрачности и преобразования кисти.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельца (pParentTarget).  
  
##  <a name="destroy"></a>CD2DGradientBrush::destroy  
 Уничтожает объект CD2DGradientBrush.  
  
```  
virtual void Destroy();
```  
  
##  <a name="m_argradientstops"></a>CD2DGradientBrush::m_arGradientStops  
 Массив структур D2D1_GRADIENT_STOP.  
  
```  
CArray<D2D1_GRADIENT_STOP, D2D1_GRADIENT_STOP> m_arGradientStops;  
```  
  
##  <a name="m_colorinterpolationgamma"></a>CD2DGradientBrush::m_colorInterpolationGamma  
 Место на диске, в какой цвет выполняется интерполяцию между позиции градиента.  
  
```  
D2D1_GAMMA m_colorInterpolationGamma;  
```  
  
##  <a name="m_extendmode"></a>CD2DGradientBrush::m_extendMode  
 Поведение вне диапазона [0,1] нормализованный градиента.  
  
```  
D2D1_EXTEND_MODE m_extendMode;  
```  
  
##  <a name="m_pgradientstops"></a>CD2DGradientBrush::m_pGradientStops  
 Указатель на массив структур D2D1_GRADIENT_STOP.  
  
```  
ID2D1GradientStopCollection* m_pGradientStops;  
```  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
