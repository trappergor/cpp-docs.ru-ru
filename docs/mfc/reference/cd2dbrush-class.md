---
title: Класс CD2DBrush | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CD2DBrush [MFC], CD2DBrush
- CD2DBrush [MFC], Attach
- CD2DBrush [MFC], Destroy
- CD2DBrush [MFC], Detach
- CD2DBrush [MFC], Get
- CD2DBrush [MFC], GetOpacity
- CD2DBrush [MFC], GetTransform
- CD2DBrush [MFC], IsValid
- CD2DBrush [MFC], SetOpacity
- CD2DBrush [MFC], SetTransform
- CD2DBrush [MFC], m_pBrush
- CD2DBrush [MFC], m_pBrushProperties
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 324e6411673a509bdf75954634ff9c6dffc5ce1f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354430"
---
# <a name="cd2dbrush-class"></a>Класс CD2DBrush
Программа-оболочка для ID2D1Brush.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DBrush : public CD2DResource;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBrush::CD2DBrush](#cd2dbrush)|Создает объект CD2DBrush.|  
|[CD2DBrush:: ~ CD2DBrush](#_dtorcd2dbrush)|Деструктор Вызывается при уничтожении объекта D2D кисти.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBrush::Attach](#attach)|Присоединяет существующий ресурс интерфейс для объекта|  
|[CD2DBrush::destroy](#destroy)|Уничтожает объект CD2DBrush. (Переопределяет [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DBrush::Detach](#detach)|Отсоединяет интерфейса ресурсов из объекта|  
|[CD2DBrush::Get](#get)|Возвращает интерфейс ID2D1Brush|  
|[CD2DBrush::GetOpacity](#getopacity)|Возвращает уровень прозрачности этой кисти|  
|[CD2DBrush::GetTransform](#gettransform)|Получает текущее преобразование целевого объекта отрисовки|  
|[CD2DBrush::IsValid](#isvalid)|Проверяет допустимость ресурсов (переопределяет [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DBrush::SetOpacity](#setopacity)|Задает уровень непрозрачности этой кисти|  
|[CD2DBrush::SetTransform](#settransform)|Применяет указанное преобразование в целевом объекте отрисовки, заменив существующий преобразования. Все последующие операции рисования происходят в преобразованный места|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBrush::operator ID2D1Brush *](#operator_id2d1brush_star)|Возвращает интерфейс ID2D1Brush|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание|  
|----------|-----------------|  
|[CD2DBrush::m_pBrush](#m_pbrush)|Хранит указатель на объект ID2D1Brush.|  
|[CD2DBrush::m_pBrushProperties](#m_pbrushproperties)|Свойства кисти.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DBrush`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="_dtorcd2dbrush"></a>  CD2DBrush:: ~ CD2DBrush  
 Деструктор Вызывается при уничтожении объекта D2D кисти.  
  
```  
virtual ~CD2DBrush();
```  
  
##  <a name="attach"></a>  CD2DBrush::Attach  
 Присоединяет существующий ресурс интерфейс для объекта  
  
```  
void Attach(ID2D1Brush* pResource);
```  
  
### <a name="parameters"></a>Параметры  
 `pResource`  
 Интерфейс существующего ресурса. Не может иметь значение NULL  
  
##  <a name="cd2dbrush"></a>  CD2DBrush::CD2DBrush  
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
 Указатель непрозрачности и преобразования кисти.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельца (pParentTarget).  
  
##  <a name="destroy"></a>  CD2DBrush::destroy  
 Уничтожает объект CD2DBrush.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>  CD2DBrush::Detach  
 Отсоединяет интерфейса ресурсов из объекта  
  
```  
ID2D1Brush* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс отсоединенных ресурсов.  
  
##  <a name="get"></a>  CD2DBrush::Get  
 Возвращает интерфейс ID2D1Brush  
  
```  
ID2D1Brush* Get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1Brush или значение NULL, если объект еще не инициализирован.  
  
##  <a name="getopacity"></a>  CD2DBrush::GetOpacity  
 Возвращает уровень прозрачности этой кисти  
  
```  
FLOAT GetOpacity() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение между 0 и 1, указывающее степень непрозрачности кисти. Это значение является константой множитель, линейно Масштабирует значения альфа все пиксели, заполненные кистью. Перед их умножением значений непрозрачности приводится в диапазоне от 0 до 1  
  
##  <a name="gettransform"></a>  CD2DBrush::GetTransform  
 Получает текущее преобразование целевого объекта отрисовки  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `transform`  
 По возвращении из этого содержит текущего преобразования целевого объекта отрисовки. Этот параметр передается неинициализированным  
  
##  <a name="isvalid"></a>  CD2DBrush::IsValid  
 Проверяет допустимость ресурсов  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ресурс является допустимым; в противном случае — значение FALSE.  
  
##  <a name="m_pbrush"></a>  CD2DBrush::m_pBrush  
 Хранит указатель на объект ID2D1Brush.  
  
```  
ID2D1Brush* m_pBrush;  
```  
  
##  <a name="m_pbrushproperties"></a>  CD2DBrush::m_pBrushProperties  
 Свойства кисти.  
  
```  
CD2DBrushProperties* m_pBrushProperties;  
```  
  
##  <a name="operator_id2d1brush_star"></a>  CD2DBrush::operator ID2D1Brush *  
 Возвращает интерфейс ID2D1Brush  
  
```  
operator ID2D1Brush*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1Brush или значение NULL, если объект еще не инициализирован.  
  
##  <a name="setopacity"></a>  CD2DBrush::SetOpacity  
 Задает уровень непрозрачности этой кисти  
  
```  
void SetOpacity(FLOAT opacity);
```  
  
### <a name="parameters"></a>Параметры  
 `opacity`  
 Значение между 0 и 1, указывающее степень непрозрачности кисти. Это значение является константой множитель, линейно Масштабирует значения альфа все пиксели, заполненные кистью. Перед их умножением значений непрозрачности приводится в диапазоне от 0 до 1  
  
##  <a name="settransform"></a>  CD2DBrush::SetTransform  
 Применяет указанное преобразование в целевом объекте отрисовки, заменив существующий преобразования. Все последующие операции рисования происходят в преобразованный места  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>Параметры  
 `transform`  
 Преобразования для применения в целевом объекте отрисовки  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
