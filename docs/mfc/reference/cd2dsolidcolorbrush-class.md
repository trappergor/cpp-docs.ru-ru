---
title: "Класс CD2DSolidColorBrush | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DSolidColorBrush
- afxrendertarget/CD2DSolidColorBrush
dev_langs:
- C++
helpviewer_keywords:
- CD2DSolidColorBrush class
ms.assetid: d4506637-acce-4f74-8a9b-f0a45571a735
caps.latest.revision: 16
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
ms.openlocfilehash: 5b6cbd6a6a5557f5ea23c0556a4b87011b510411
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dsolidcolorbrush-class"></a>Класс CD2DSolidColorBrush
Программа-оболочка для ID2D1SolidColorBrush.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DSolidColorBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DSolidColorBrush::CD2DSolidColorBrush](#cd2dsolidcolorbrush)|Перегружен. Создает объект CD2DSolidColorBrush.|  
|[CD2DSolidColorBrush:: ~ CD2DSolidColorBrush](#cd2dsolidcolorbrush__~cd2dsolidcolorbrush)|Деструктор Вызывается при уничтожении объекта D2D сплошной кисти.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DSolidColorBrush::Attach](#attach)|Присоединение существующих ресурсов интерфейса в объект|  
|[CD2DSolidColorBrush::CREATE](#create)|Создает CD2DSolidColorBrush. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DSolidColorBrush::destroy](#destroy)|Уничтожает объект CD2DSolidColorBrush. (Переопределяет [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|  
|[CD2DSolidColorBrush::Detach](#detach)|Отсоединяет интерфейс ресурса из объекта|  
|[CD2DSolidColorBrush::Get](#get)|Возвращает интерфейс ID2D1SolidColorBrush|  
|[CD2DSolidColorBrush::GetColor](#getcolor)|Получает цвет сплошной цвет кисти|  
|[CD2DSolidColorBrush::SetColor](#setcolor)|Указывает цвет этого Одноцветная кисть|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DSolidColorBrush::operator ID2D1SolidColorBrush *](#operator_id2d1solidcolorbrush_star)|Возвращает интерфейс ID2D1SolidColorBrush|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DSolidColorBrush::m_colorSolid](#m_colorsolid)|Сплошной цвет кисти.|  
|[CD2DSolidColorBrush::m_pSolidColorBrush](#m_psolidcolorbrush)|Хранит указатель на объект ID2D1SolidColorBrush.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DSolidColorBrush](../../mfc/reference/cd2dsolidcolorbrush-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dsolidcolorbrusha--cd2dsolidcolorbrushcd2dsolidcolorbrush"></a><a name="_dtorcd2dsolidcolorbrush"></a>CD2DSolidColorBrush:: ~ CD2DSolidColorBrush  
 Деструктор Вызывается при уничтожении объекта D2D сплошной кисти.  
  
```  
virtual ~CD2DSolidColorBrush();
```  
  
##  <a name="a-nameattacha--cd2dsolidcolorbrushattach"></a><a name="attach"></a>CD2DSolidColorBrush::Attach  
 Присоединение существующих ресурсов интерфейса в объект  
  
```  
void Attach(ID2D1SolidColorBrush* pResource);
```  
  
### <a name="parameters"></a>Параметры  
 `pResource`  
 Существующий интерфейс ресурсов. Не может иметь значение NULL  
  
##  <a name="a-namecd2dsolidcolorbrusha--cd2dsolidcolorbrushcd2dsolidcolorbrush"></a><a name="cd2dsolidcolorbrush"></a>CD2DSolidColorBrush::CD2DSolidColorBrush  
 Создает объект CD2DSolidColorBrush.  
  
```  
CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,  
    D2D1_COLOR_F color,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);

 
CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,  
    COLORREF color,  
    int nAlpha = 255,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentTarget`  
 Указатель на целевой объект отрисовки.  
  
 `color`  
 Красный, зеленый, синий и альфа-значения цвет кисти.  
  
 `pBrushProperties`  
 Указатель непрозрачности и преобразование кисти.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельцем (pParentTarget).  
  
 `nAlpha`  
 Непрозрачность цвета кисти.  
  
##  <a name="a-namecreatea--cd2dsolidcolorbrushcreate"></a><a name="create"></a>CD2DSolidColorBrush::CREATE  
 Создает CD2DSolidColorBrush.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pRenderTarget`  
 Указатель на целевой объект отрисовки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. В противном случае — возвращает код ошибки HRESULT.  
  
##  <a name="a-namedestroya--cd2dsolidcolorbrushdestroy"></a><a name="destroy"></a>CD2DSolidColorBrush::destroy  
 Уничтожает объект CD2DSolidColorBrush.  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namedetacha--cd2dsolidcolorbrushdetach"></a><a name="detach"></a>CD2DSolidColorBrush::Detach  
 Отсоединяет интерфейс ресурса из объекта  
  
```  
ID2D1SolidColorBrush* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс отсоединенных ресурсов.  
  
##  <a name="a-namegeta--cd2dsolidcolorbrushget"></a><a name="get"></a>CD2DSolidColorBrush::Get  
 Возвращает интерфейс ID2D1SolidColorBrush  
  
```  
ID2D1SolidColorBrush* Get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1SolidColorBrush или значение NULL, если объект еще не инициализирован.  
  
##  <a name="a-namegetcolora--cd2dsolidcolorbrushgetcolor"></a><a name="getcolor"></a>CD2DSolidColorBrush::GetColor  
 Получает цвет сплошной цвет кисти  
  
```  
D2D1_COLOR_F GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет этой Одноцветная кисть  
  
##  <a name="a-namemcolorsolida--cd2dsolidcolorbrushmcolorsolid"></a><a name="m_colorsolid"></a>CD2DSolidColorBrush::m_colorSolid  
 Сплошной цвет кисти.  
  
```  
D2D1_COLOR_F m_colorSolid;  
```  
  
##  <a name="a-namempsolidcolorbrusha--cd2dsolidcolorbrushmpsolidcolorbrush"></a><a name="m_psolidcolorbrush"></a>CD2DSolidColorBrush::m_pSolidColorBrush  
 Хранит указатель на объект ID2D1SolidColorBrush.  
  
```  
ID2D1SolidColorBrush* m_pSolidColorBrush;  
```  
  
##  <a name="a-nameoperatorid2d1solidcolorbrushstara--cd2dsolidcolorbrushoperator-id2d1solidcolorbrush"></a><a name="operator_id2d1solidcolorbrush_star"></a>CD2DSolidColorBrush::operator ID2D1SolidColorBrush *  
 Возвращает интерфейс ID2D1SolidColorBrush  
  
```  
operator ID2D1SolidColorBrush*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1SolidColorBrush или значение NULL, если объект еще не инициализирован.  
  
##  <a name="a-namesetcolora--cd2dsolidcolorbrushsetcolor"></a><a name="setcolor"></a>CD2DSolidColorBrush::SetColor  
 Указывает цвет этого Одноцветная кисть  
  
```  
void SetColor(D2D1_COLOR_F color);
```  
  
### <a name="parameters"></a>Параметры  
 `color`  
 Цвет этой Одноцветная кисть  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

