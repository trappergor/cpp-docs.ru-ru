---
title: "Класс CD2DBitmapBrush | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::Attach
- AFXRENDERTARGET/CD2DBitmapBrush::Create
- AFXRENDERTARGET/CD2DBitmapBrush::Destroy
- AFXRENDERTARGET/CD2DBitmapBrush::Detach
- AFXRENDERTARGET/CD2DBitmapBrush::Get
- AFXRENDERTARGET/CD2DBitmapBrush::GetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::GetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::SetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::SetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::CommonInit
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrushProperties
dev_langs: C++
helpviewer_keywords:
- CD2DBitmapBrush [MFC], CD2DBitmapBrush
- CD2DBitmapBrush [MFC], Attach
- CD2DBitmapBrush [MFC], Create
- CD2DBitmapBrush [MFC], Destroy
- CD2DBitmapBrush [MFC], Detach
- CD2DBitmapBrush [MFC], Get
- CD2DBitmapBrush [MFC], GetBitmap
- CD2DBitmapBrush [MFC], GetExtendModeX
- CD2DBitmapBrush [MFC], GetExtendModeY
- CD2DBitmapBrush [MFC], GetInterpolationMode
- CD2DBitmapBrush [MFC], SetBitmap
- CD2DBitmapBrush [MFC], SetExtendModeX
- CD2DBitmapBrush [MFC], SetExtendModeY
- CD2DBitmapBrush [MFC], SetInterpolationMode
- CD2DBitmapBrush [MFC], CommonInit
- CD2DBitmapBrush [MFC], m_pBitmap
- CD2DBitmapBrush [MFC], m_pBitmapBrush
- CD2DBitmapBrush [MFC], m_pBitmapBrushProperties
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3dd588a26b73fb6e5f1b205b20f21aab8272c439
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cd2dbitmapbrush-class"></a>Класс CD2DBitmapBrush
Программа-оболочка для ID2D1BitmapBrush.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DBitmapBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DBitmapBrush::CD2DBitmapBrush](#cd2dbitmapbrush)|Перегружен. Создает объект CD2DBitmapBrush из файла.|  
|[CD2DBitmapBrush:: ~ CD2DBitmapBrush](#dtor)|Деструктор Вызывается при уничтожении объекта D2D кисти растрового изображения.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DBitmapBrush::Attach](#attach)|Присоединяет существующий ресурс интерфейс для объекта|  
|[CD2DBitmapBrush::CREATE](#create)|Создает CD2DBitmapBrush. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DBitmapBrush::destroy](#destroy)|Уничтожает объект CD2DBitmapBrush. (Переопределяет [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|  
|[CD2DBitmapBrush::Detach](#detach)|Отсоединяет интерфейса ресурсов из объекта|  
|[CD2DBitmapBrush::Get](#get)|Возвращает интерфейс ID2D1BitmapBrush|  
|[CD2DBitmapBrush::GetBitmap](#getbitmap)|Возвращает растровое изображение источника, который использует данную кисть для рисования|  
|[CD2DBitmapBrush::GetExtendModeX](#getextendmodex)|Возвращает метод, с помощью которого кисть по горизонтали плитки тех областей, которые выходящих за его растрового изображения|  
|[CD2DBitmapBrush::GetExtendModeY](#getextendmodey)|Возвращает метод, с помощью которого кисть по вертикали плитки тех областей, которые выходящих за его растрового изображения|  
|[CD2DBitmapBrush::GetInterpolationMode](#getinterpolationmode)|Возвращает метод интерполяции, используемый при повернутых или масштабированных кисти точечного рисунка|  
|[CD2DBitmapBrush::SetBitmap](#setbitmap)|Источник точечного рисунка, который использует данную кисть для рисования|  
|[CD2DBitmapBrush::SetExtendModeX](#setextendmodex)|Указывает, как кисть по горизонтали плитки тех областей, которые выходящих за его растрового изображения|  
|[CD2DBitmapBrush::SetExtendModeY](#setextendmodey)|Указывает, как кисть по вертикали плитки тех областей, которые выходящих за его растрового изображения|  
|[CD2DBitmapBrush::SetInterpolationMode](#setinterpolationmode)|Указывает режим интерполяции, используемый при повернутых или масштабированных кисти точечного рисунка|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DBitmapBrush::CommonInit](#commoninit)|Инициализирует объект|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DBitmapBrush::operator ID2D1BitmapBrush *](#operator_id2d1bitmapbrush_star)|Возвращает интерфейс ID2D1BitmapBrush|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CD2DBitmapBrush::m_pBitmap](#m_pbitmap)|Содержит указатель на объект CD2DBitmap.|  
|[CD2DBitmapBrush::m_pBitmapBrush](#m_pbitmapbrush)|Хранит указатель на объект ID2D1BitmapBrush.|  
|[CD2DBitmapBrush::m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|Битовая карта, свойства кисти.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 `CD2DBitmapBrush`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="dtor"></a>CD2DBitmapBrush:: ~ CD2DBitmapBrush  
 Деструктор Вызывается при уничтожении объекта D2D кисти растрового изображения.  
  
```  
virtual ~CD2DBitmapBrush();
```  
  
##  <a name="attach"></a>CD2DBitmapBrush::Attach  
 Присоединяет существующий ресурс интерфейс для объекта  
  
```  
void Attach(ID2D1BitmapBrush* pResource);
```  
  
### <a name="parameters"></a>Параметры  
 `pResource`  
 Интерфейс существующего ресурса. Не может иметь значение NULL  
  
##  <a name="cd2dbitmapbrush"></a>CD2DBitmapBrush::CD2DBitmapBrush  
 Создает объект CD2DBitmapBrush.  
  
```  
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    UINT uiResID,  
    LPCTSTR lpszType = NULL,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    LPCTSTR lpszImagePath,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentTarget`  
 Указатель на целевой объект отрисовки.  
  
 `pBitmapBrushProperties`  
 Указатель на режимы расширить и режим интерполяции кисти растрового изображения.  
  
 `pBrushProperties`  
 Указатель непрозрачности и преобразования кисти.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельца (pParentTarget).  
  
 `uiResID`  
 Идентификационный номер ресурса ресурса.  
  
 `lpszType`  
 Указатель null нулевым байтом строка, содержащая тип ресурса.  
  
 `sizeDest`  
 Целевой размер растрового изображения.  
  
 `lpszImagePath`  
 Указатель на завершающуюся значением null строка, содержащая имя файла.  
  
##  <a name="commoninit"></a>CD2DBitmapBrush::CommonInit  
 Инициализирует объект  
  
```  
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```  
  
### <a name="parameters"></a>Параметры  
 `pBitmapBrushProperties`  
 Указатель свойства кисти растрового изображения.  
  
##  <a name="create"></a>CD2DBitmapBrush::CREATE  
 Создает CD2DBitmapBrush.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pRenderTarget`  
 Указатель на целевой объект отрисовки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. В противном случае возвращается код ошибки HRESULT.  
  
##  <a name="destroy"></a>CD2DBitmapBrush::destroy  
 Уничтожает объект CD2DBitmapBrush.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DBitmapBrush::Detach  
 Отсоединяет интерфейса ресурсов из объекта  
  
```  
ID2D1BitmapBrush* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс отсоединенных ресурсов.  
  
##  <a name="get"></a>CD2DBitmapBrush::Get  
 Возвращает интерфейс ID2D1BitmapBrush  
  
```  
ID2D1BitmapBrush* Get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1BitmapBrush или значение NULL, если объект еще не инициализирован.  
  
##  <a name="getbitmap"></a>CD2DBitmapBrush::GetBitmap  
 Возвращает растровое изображение источника, который использует данную кисть для рисования  
  
```  
CD2DBitmap* GetBitmap();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект CD2DBitmap или значение NULL, если объект еще не инициализирован.  
  
##  <a name="getextendmodex"></a>CD2DBitmapBrush::GetExtendModeX  
 Возвращает метод, с помощью которого кисть по горизонтали плитки тех областей, которые выходящих за его растрового изображения  
  
```  
D2D1_EXTEND_MODE GetExtendModeX() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, указывающее, как кисть по горизонтали плитки тех областей, которые выходящих за его растрового изображения  
  
##  <a name="getextendmodey"></a>CD2DBitmapBrush::GetExtendModeY  
 Возвращает метод, с помощью которого кисть по вертикали плитки тех областей, которые выходящих за его растрового изображения  
  
```  
D2D1_EXTEND_MODE GetExtendModeY() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, указывающее, как кисть по вертикали плитки тех областей, которые выходящих за его растрового изображения  
  
##  <a name="getinterpolationmode"></a>CD2DBitmapBrush::GetInterpolationMode  
 Возвращает метод интерполяции, используемый при повернутых или масштабированных кисти точечного рисунка  
  
```  
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Метод интерполяции, использовавшейся повернутых или масштабированных кисти точечного рисунка  
  
##  <a name="m_pbitmap"></a>CD2DBitmapBrush::m_pBitmap  
 Содержит указатель на объект CD2DBitmap.  
  
```  
CD2DBitmap* m_pBitmap;  
```  
  
##  <a name="m_pbitmapbrush"></a>CD2DBitmapBrush::m_pBitmapBrush  
 Хранит указатель на объект ID2D1BitmapBrush.  
  
```  
ID2D1BitmapBrush* m_pBitmapBrush;  
```  
  
##  <a name="m_pbitmapbrushproperties"></a>CD2DBitmapBrush::m_pBitmapBrushProperties  
 Битовая карта, свойства кисти.  
  
```  
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;  
```  
  
##  <a name="operator_id2d1bitmapbrush_star"></a>CD2DBitmapBrush::operator ID2D1BitmapBrush *  
 Возвращает интерфейс ID2D1BitmapBrush  
  
```  
operator ID2D1BitmapBrush*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1BitmapBrush или значение NULL, если объект еще не инициализирован.  
  
##  <a name="setbitmap"></a>CD2DBitmapBrush::SetBitmap  
 Источник точечного рисунка, который использует данную кисть для рисования  
  
```  
void SetBitmap(CD2DBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Параметры  
 `pBitmap`  
 Источник растрового изображения, используемые кисти  
  
##  <a name="setextendmodex"></a>CD2DBitmapBrush::SetExtendModeX  
 Указывает, как кисть по горизонтали плитки тех областей, которые выходящих за его растрового изображения  
  
```  
void SetExtendModeX(D2D1_EXTEND_MODE extendModeX);
```  
  
### <a name="parameters"></a>Параметры  
 `extendModeX`  
 Значение, указывающее, как кисть по горизонтали плитки тех областей, которые выходящих за его растрового изображения  
  
##  <a name="setextendmodey"></a>CD2DBitmapBrush::SetExtendModeY  
 Указывает, как кисть по вертикали плитки тех областей, которые выходящих за его растрового изображения  
  
```  
void SetExtendModeY(D2D1_EXTEND_MODE extendModeY);
```  
  
### <a name="parameters"></a>Параметры  
 `extendModeY`  
 Значение, указывающее, как кисть по вертикали плитки тех областей, которые выходящих за его растрового изображения  
  
##  <a name="setinterpolationmode"></a>CD2DBitmapBrush::SetInterpolationMode  
 Указывает режим интерполяции, используемый при повернутых или масштабированных кисти точечного рисунка  
  
```  
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```  
  
### <a name="parameters"></a>Параметры  
 `interpolationMode`  
 Режим интерполяции, используемый при повернутых или масштабированных кисти точечного рисунка  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
