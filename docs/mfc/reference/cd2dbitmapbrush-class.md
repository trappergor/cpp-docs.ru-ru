---
title: "Класс CD2DBitmapBrush | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DBitmapBrush
- afxrendertarget/CD2DBitmapBrush
dev_langs:
- C++
helpviewer_keywords:
- CD2DBitmapBrush class
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
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
ms.openlocfilehash: a9ab15dcae8715b98cc9f723a710b64e83649bf9
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dbitmapbrush-class"></a>Класс CD2DBitmapBrush
Программа-оболочка для ID2D1BitmapBrush.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DBitmapBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBitmapBrush::CD2DBitmapBrush](#cd2dbitmapbrush)|Перегружен. Создает объект CD2DBitmapBrush из файла.|  
|[CD2DBitmapBrush:: ~ CD2DBitmapBrush](#dtor)|Деструктор Вызывается при уничтожении объекта D2D точечный рисунок кисти.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBitmapBrush::Attach](#attach)|Присоединение существующих ресурсов интерфейса в объект|  
|[CD2DBitmapBrush::CREATE](#create)|Создает CD2DBitmapBrush. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DBitmapBrush::destroy](#destroy)|Уничтожает объект CD2DBitmapBrush. (Переопределяет [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|  
|[CD2DBitmapBrush::Detach](#detach)|Отсоединяет интерфейс ресурса из объекта|  
|[CD2DBitmapBrush::Get](#get)|Возвращает интерфейс ID2D1BitmapBrush|  
|[CD2DBitmapBrush::GetBitmap](#getbitmap)|Возвращает источник растрового изображения, который использует данную кисть для закрашивания|  
|[CD2DBitmapBrush::GetExtendModeX](#getextendmodex)|Возвращает метод, с помощью которого кисть по горизонтали плитки тех областей, которые выходить за его точечного рисунка|  
|[CD2DBitmapBrush::GetExtendModeY](#getextendmodey)|Возвращает метод, с помощью которого кисть по вертикали плитки тех областей, которые выходить за его точечного рисунка|  
|[CD2DBitmapBrush::GetInterpolationMode](#getinterpolationmode)|Возвращает метод интерполяции, используемый при повернутых или масштабированных точечный рисунок кисти|  
|[CD2DBitmapBrush::SetBitmap](#setbitmap)|Указывает источник точечного рисунка, который использует данную кисть для закрашивания|  
|[CD2DBitmapBrush::SetExtendModeX](#setextendmodex)|Указывает, как кисть по горизонтали плитки тех областей, которые выходить за его точечного рисунка|  
|[CD2DBitmapBrush::SetExtendModeY](#setextendmodey)|Указывает, как кисть по вертикали плитки тех областей, которые выходить за его точечного рисунка|  
|[CD2DBitmapBrush::SetInterpolationMode](#setinterpolationmode)|Указывает режим интерполяции, используемый при повернутых или масштабированных точечный рисунок кисти|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBitmapBrush::CommonInit](#commoninit)|Инициализирует объект|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBitmapBrush::operator ID2D1BitmapBrush *](#operator_id2d1bitmapbrush_star)|Возвращает интерфейс ID2D1BitmapBrush|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBitmapBrush::m_pBitmap](#m_pbitmap)|Хранит указатель на объект CD2DBitmap.|  
|[CD2DBitmapBrush::m_pBitmapBrush](#m_pbitmapbrush)|Хранит указатель на объект ID2D1BitmapBrush.|  
|[CD2DBitmapBrush::m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|Битовая карта, свойства кисти.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 `CD2DBitmapBrush`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="a-namedtora--cd2dbitmapbrushcd2dbitmapbrush"></a><a name="dtor"></a>CD2DBitmapBrush:: ~ CD2DBitmapBrush  
 Деструктор Вызывается при уничтожении объекта D2D точечный рисунок кисти.  
  
```  
virtual ~CD2DBitmapBrush();
```  
  
##  <a name="a-nameattacha--cd2dbitmapbrushattach"></a><a name="attach"></a>CD2DBitmapBrush::Attach  
 Присоединение существующих ресурсов интерфейса в объект  
  
```  
void Attach(ID2D1BitmapBrush* pResource);
```  
  
### <a name="parameters"></a>Параметры  
 `pResource`  
 Существующий интерфейс ресурсов. Не может иметь значение NULL  
  
##  <a name="a-namecd2dbitmapbrusha--cd2dbitmapbrushcd2dbitmapbrush"></a><a name="cd2dbitmapbrush"></a>CD2DBitmapBrush::CD2DBitmapBrush  
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
 Указатель на режимы расширить и режим интерполяции кисти точечного рисунка.  
  
 `pBrushProperties`  
 Указатель непрозрачности и преобразование кисти.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельцем (pParentTarget).  
  
 `uiResID`  
 Идентификационный номер ресурса ресурса.  
  
 `lpszType`  
 Указатель нулем строка, содержащая тип ресурса.  
  
 `sizeDest`  
 Целевой размер растрового изображения.  
  
 `lpszImagePath`  
 Указатель нулем строка, содержащая имя файла.  
  
##  <a name="a-namecommoninita--cd2dbitmapbrushcommoninit"></a><a name="commoninit"></a>CD2DBitmapBrush::CommonInit  
 Инициализирует объект  
  
```  
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```  
  
### <a name="parameters"></a>Параметры  
 `pBitmapBrushProperties`  
 Указатель свойства кисти растрового изображения.  
  
##  <a name="a-namecreatea--cd2dbitmapbrushcreate"></a><a name="create"></a>CD2DBitmapBrush::CREATE  
 Создает CD2DBitmapBrush.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pRenderTarget`  
 Указатель на целевой объект отрисовки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. В противном случае — возвращает код ошибки HRESULT.  
  
##  <a name="a-namedestroya--cd2dbitmapbrushdestroy"></a><a name="destroy"></a>CD2DBitmapBrush::destroy  
 Уничтожает объект CD2DBitmapBrush.  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namedetacha--cd2dbitmapbrushdetach"></a><a name="detach"></a>CD2DBitmapBrush::Detach  
 Отсоединяет интерфейс ресурса из объекта  
  
```  
ID2D1BitmapBrush* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс отсоединенных ресурсов.  
  
##  <a name="a-namegeta--cd2dbitmapbrushget"></a><a name="get"></a>CD2DBitmapBrush::Get  
 Возвращает интерфейс ID2D1BitmapBrush  
  
```  
ID2D1BitmapBrush* Get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1BitmapBrush или значение NULL, если объект еще не инициализирован.  
  
##  <a name="a-namegetbitmapa--cd2dbitmapbrushgetbitmap"></a><a name="getbitmap"></a>CD2DBitmapBrush::GetBitmap  
 Возвращает источник растрового изображения, который использует данную кисть для закрашивания  
  
```  
CD2DBitmap* GetBitmap();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на CD2DBitmap объект или значение NULL, если объект еще не инициализирован.  
  
##  <a name="a-namegetextendmodexa--cd2dbitmapbrushgetextendmodex"></a><a name="getextendmodex"></a>CD2DBitmapBrush::GetExtendModeX  
 Возвращает метод, с помощью которого кисть по горизонтали плитки тех областей, которые выходить за его точечного рисунка  
  
```  
D2D1_EXTEND_MODE GetExtendModeX() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, указывающее, как кисть по горизонтали плитки тех областей, которые выходить за его точечного рисунка  
  
##  <a name="a-namegetextendmodeya--cd2dbitmapbrushgetextendmodey"></a><a name="getextendmodey"></a>CD2DBitmapBrush::GetExtendModeY  
 Возвращает метод, с помощью которого кисть по вертикали плитки тех областей, которые выходить за его точечного рисунка  
  
```  
D2D1_EXTEND_MODE GetExtendModeY() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, указывающее, как кисть по вертикали плитки тех областей, которые выходить за его точечного рисунка  
  
##  <a name="a-namegetinterpolationmodea--cd2dbitmapbrushgetinterpolationmode"></a><a name="getinterpolationmode"></a>CD2DBitmapBrush::GetInterpolationMode  
 Возвращает метод интерполяции, используемый при повернутых или масштабированных точечный рисунок кисти  
  
```  
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Метод интерполяции, который используется при повернутых или масштабированных точечный рисунок кисти  
  
##  <a name="a-namempbitmapa--cd2dbitmapbrushmpbitmap"></a><a name="m_pbitmap"></a>CD2DBitmapBrush::m_pBitmap  
 Хранит указатель на объект CD2DBitmap.  
  
```  
CD2DBitmap* m_pBitmap;  
```  
  
##  <a name="a-namempbitmapbrusha--cd2dbitmapbrushmpbitmapbrush"></a><a name="m_pbitmapbrush"></a>CD2DBitmapBrush::m_pBitmapBrush  
 Хранит указатель на объект ID2D1BitmapBrush.  
  
```  
ID2D1BitmapBrush* m_pBitmapBrush;  
```  
  
##  <a name="a-namempbitmapbrushpropertiesa--cd2dbitmapbrushmpbitmapbrushproperties"></a><a name="m_pbitmapbrushproperties"></a>CD2DBitmapBrush::m_pBitmapBrushProperties  
 Битовая карта, свойства кисти.  
  
```  
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;  
```  
  
##  <a name="a-nameoperatorid2d1bitmapbrushstara--cd2dbitmapbrushoperator-id2d1bitmapbrush"></a><a name="operator_id2d1bitmapbrush_star"></a>CD2DBitmapBrush::operator ID2D1BitmapBrush *  
 Возвращает интерфейс ID2D1BitmapBrush  
  
```  
operator ID2D1BitmapBrush*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1BitmapBrush или значение NULL, если объект еще не инициализирован.  
  
##  <a name="a-namesetbitmapa--cd2dbitmapbrushsetbitmap"></a><a name="setbitmap"></a>CD2DBitmapBrush::SetBitmap  
 Указывает источник точечного рисунка, который использует данную кисть для закрашивания  
  
```  
void SetBitmap(CD2DBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Параметры  
 `pBitmap`  
 Источник растрового изображения, используемые кисти  
  
##  <a name="a-namesetextendmodexa--cd2dbitmapbrushsetextendmodex"></a><a name="setextendmodex"></a>CD2DBitmapBrush::SetExtendModeX  
 Указывает, как кисть по горизонтали плитки тех областей, которые выходить за его точечного рисунка  
  
```  
void SetExtendModeX(D2D1_EXTEND_MODE extendModeX);
```  
  
### <a name="parameters"></a>Параметры  
 `extendModeX`  
 Значение, указывающее, как кисть по горизонтали плитки тех областей, которые выходить за его точечного рисунка  
  
##  <a name="a-namesetextendmodeya--cd2dbitmapbrushsetextendmodey"></a><a name="setextendmodey"></a>CD2DBitmapBrush::SetExtendModeY  
 Указывает, как кисть по вертикали плитки тех областей, которые выходить за его точечного рисунка  
  
```  
void SetExtendModeY(D2D1_EXTEND_MODE extendModeY);
```  
  
### <a name="parameters"></a>Параметры  
 `extendModeY`  
 Значение, указывающее, как кисть по вертикали плитки тех областей, которые выходить за его точечного рисунка  
  
##  <a name="a-namesetinterpolationmodea--cd2dbitmapbrushsetinterpolationmode"></a><a name="setinterpolationmode"></a>CD2DBitmapBrush::SetInterpolationMode  
 Указывает режим интерполяции, используемый при повернутых или масштабированных точечный рисунок кисти  
  
```  
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```  
  
### <a name="parameters"></a>Параметры  
 `interpolationMode`  
 Режим интерполяции, используемый при повернутых или масштабированных точечный рисунок кисти  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

