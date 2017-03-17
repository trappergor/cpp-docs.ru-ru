---
title: "Класс CD2DBrush | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DBrush
- AFXRENDERTARGET/CD2DBrush
- AFXRENDERTARGET/CD2DBrush::CD2DBrush
- AFXRENDERTARGET/CD2DBrush::Attach
- AFXRENDERTARGET/CD2DBrush::Destroy
- AFXRENDERTARGET/CD2DBrush::Detach
- AFXRENDERTARGET/CD2DBrush::Get
- AFXRENDERTARGET/CD2DBrush::GetOpacity
- AFXRENDERTARGET/CD2DBrush::GetTransform
- AFXRENDERTARGET/CD2DBrush::IsValid
- AFXRENDERTARGET/CD2DBrush::SetOpacity
- AFXRENDERTARGET/CD2DBrush::SetTransform
- AFXRENDERTARGET/CD2DBrush::m_pBrush
- AFXRENDERTARGET/CD2DBrush::m_pBrushProperties
dev_langs:
- C++
helpviewer_keywords:
- CD2DBrush class
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
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
ms.openlocfilehash: b9902445fb6e18df20073d132a2117c67e695b25
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dbrush-class"></a>Класс CD2DBrush
Программа-оболочка для ID2D1Brush.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DBrush : public CD2DResource;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBrush::CD2DBrush](#cd2dbrush)|Создает объект CD2DBrush.|  
|[CD2DBrush:: ~ CD2DBrush](#_dtorcd2dbrush)|Деструктор Вызывается при уничтожении объекта D2D кисти.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBrush::Attach](#attach)|Присоединение существующих ресурсов интерфейса в объект|  
|[CD2DBrush::destroy](#destroy)|Уничтожает объект CD2DBrush. (Переопределяет [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DBrush::Detach](#detach)|Отсоединяет интерфейс ресурса из объекта|  
|[CD2DBrush::Get](#get)|Возвращает интерфейс ID2D1Brush|  
|[CD2DBrush::GetOpacity](#getopacity)|Возвращает степень непрозрачности этой кисти|  
|[CD2DBrush::GetTransform](#gettransform)|Возвращает текущее преобразование целевого объекта отрисовки|  
|[CD2DBrush::IsValid](#isvalid)|Проверяет допустимость ресурсов (переопределяет [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DBrush::SetOpacity](#setopacity)|Задает степень непрозрачности этой кисти|  
|[CD2DBrush::SetTransform](#settransform)|Применяет указанное преобразование в объект рендеринга, заменив существующее преобразование. Все последующие операции рисования происходят в преобразованные места|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBrush::operator ID2D1Brush *](#operator_id2d1brush_star)|Возвращает интерфейс ID2D1Brush|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBrush::m_pBrush](#m_pbrush)|Хранит указатель на объект ID2D1Brush.|  
|[CD2DBrush::m_pBrushProperties](#m_pbrushproperties)|Свойства кисти.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DBrush`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="_dtorcd2dbrush"></a>CD2DBrush:: ~ CD2DBrush  
 Деструктор Вызывается при уничтожении объекта D2D кисти.  
  
```  
virtual ~CD2DBrush();
```  
  
##  <a name="attach"></a>CD2DBrush::Attach  
 Присоединение существующих ресурсов интерфейса в объект  
  
```  
void Attach(ID2D1Brush* pResource);
```  
  
### <a name="parameters"></a>Параметры  
 `pResource`  
 Существующий интерфейс ресурсов. Не может иметь значение NULL  
  
##  <a name="cd2dbrush"></a>CD2DBrush::CD2DBrush  
 Создает объект CD2DBrush.  
  
```  
CD2DBrush(
    CRenderTarget* pParentTarget,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentTarget`  
 Указатель на целевой объект отрисовки.  
  
 `pBrushProperties`  
 Указатель непрозрачности и преобразование кисти.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельцем (pParentTarget).  
  
##  <a name="destroy"></a>CD2DBrush::destroy  
 Уничтожает объект CD2DBrush.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DBrush::Detach  
 Отсоединяет интерфейс ресурса из объекта  
  
```  
ID2D1Brush* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс отсоединенных ресурсов.  
  
##  <a name="get"></a>CD2DBrush::Get  
 Возвращает интерфейс ID2D1Brush  
  
```  
ID2D1Brush* Get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1Brush или значение NULL, если объект еще не инициализирован.  
  
##  <a name="getopacity"></a>CD2DBrush::GetOpacity  
 Возвращает степень непрозрачности этой кисти  
  
```  
FLOAT GetOpacity() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение между 0 и 1, указывающее, непрозрачность кисти. Это значение является константой множитель, линейно масштабирует значение альфа-канала все пиксели, заполненные кистью. Значение непрозрачности сжимается в диапазоне от 0 до 1, перед их вместе умножения  
  
##  <a name="gettransform"></a>CD2DBrush::GetTransform  
 Возвращает текущее преобразование целевого объекта отрисовки  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `transform`  
 По возвращении из этого содержит текущее преобразование целевого объекта отрисовки. Этот параметр передается неинициализированным  
  
##  <a name="isvalid"></a>CD2DBrush::IsValid  
 Проверяет допустимость ресурсов  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ресурс является допустимым; в противном случае — значение FALSE.  
  
##  <a name="m_pbrush"></a>CD2DBrush::m_pBrush  
 Хранит указатель на объект ID2D1Brush.  
  
```  
ID2D1Brush* m_pBrush;  
```  
  
##  <a name="m_pbrushproperties"></a>CD2DBrush::m_pBrushProperties  
 Свойства кисти.  
  
```  
CD2DBrushProperties* m_pBrushProperties;  
```  
  
##  <a name="operator_id2d1brush_star"></a>CD2DBrush::operator ID2D1Brush *  
 Возвращает интерфейс ID2D1Brush  
  
```  
operator ID2D1Brush*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1Brush или значение NULL, если объект еще не инициализирован.  
  
##  <a name="setopacity"></a>CD2DBrush::SetOpacity  
 Задает степень непрозрачности этой кисти  
  
```  
void SetOpacity(FLOAT opacity);
```  
  
### <a name="parameters"></a>Параметры  
 `opacity`  
 Значение между 0 и 1, указывающее, непрозрачность кисти. Это значение является константой множитель, линейно масштабирует значение альфа-канала все пиксели, заполненные кистью. Значение непрозрачности сжимается в диапазоне от 0 до 1, перед их вместе умножения  
  
##  <a name="settransform"></a>CD2DBrush::SetTransform  
 Применяет указанное преобразование в объект рендеринга, заменив существующее преобразование. Все последующие операции рисования происходят в преобразованные места  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>Параметры  
 `transform`  
 Преобразование для применения к целевой объект отрисовки  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

