---
title: Класс CD2DBrush
ms.date: 11/04/2016
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
ms.openlocfilehash: 536d84fe2c2f68d62490e1ce2b65085426762e87
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754192"
---
# <a name="cd2dbrush-class"></a>Класс CD2DBrush

Обертка для ID2D1Brush.

## <a name="syntax"></a>Синтаксис

```
class CD2DBrush : public CD2DResource;
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DBrush::CD2DBrush](#cd2dbrush)|Строит объект CD2DBrush.|
|[CD2DBrush::CD2DBrush](#_dtorcd2dbrush)|Деструктор Вызывается при уничтожении объекта кисти D2D.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DBrush::Attach](#attach)|Прикрепляет существующий интерфейс ресурса к объекту|
|[CD2DBrush::Destroy](#destroy)|Уничтожает объект CD2DBrush. (Переопределяет [CD2DРесурс::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DBrush::Detach](#detach)|Открепите интерфейс ресурса с объекта|
|[CD2DBrush::Get](#get)|Возвращает интерфейс ID2D1Brush|
|[CD2DBrush::GetOpacity](#getopacity)|Получает степень непрозрачности этой кисти|
|[CD2DBrush::GetTransform](#gettransform)|Получает текущее преобразование цели рендеринга|
|[CD2DBrush::IsValid](#isvalid)|Проверка достоверности ресурса (Переопределения [CD2DРесурса:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DBrush::SetOpacity](#setopacity)|Устанавливает степень непрозрачности этой кисти|
|[CD2DBrush::SetTransform](#settransform)|Применяет указанное преобразование к цели рендера, заменяя существующую трансформацию. Все последующие операции рисования происходят в преобразованном пространстве|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DBrush::оператор ID2D1Brush](#operator_id2d1brush_star)|Возвращает интерфейс ID2D1Brush|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CD2DBrush::m_pBrush](#m_pbrush)|Хранит указатель на объект ID2D1Brush.|
|[CD2DBrush::m_pBrushProperties](#m_pbrushproperties)|Свойства кисти.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DРесурс](../../mfc/reference/cd2dresource-class.md)

`CD2DBrush`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dbrushcd2dbrush"></a><a name="_dtorcd2dbrush"></a>CD2DBrush::CD2DBrush

Деструктор Вызывается при уничтожении объекта кисти D2D.

```
virtual ~CD2DBrush();
```

## <a name="cd2dbrushattach"></a><a name="attach"></a>CD2DBrush::Attach

Прикрепляет существующий интерфейс ресурса к объекту.

```cpp
void Attach(ID2D1Brush* pResource);
```

### <a name="parameters"></a>Параметры

*pResource*<br/>
Существующий интерфейс ресурса. Не может быть NULL.

## <a name="cd2dbrushcd2dbrush"></a><a name="cd2dbrush"></a>CD2DBrush::CD2DBrush

Строит объект CD2DBrush.

```
CD2DBrush(
    CRenderTarget* pParentTarget,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*pParentTarget*<br/>
Указатель на цель рендера.

*pBrushProperties*<br/>
Указатель на непрозрачность и трансформацию кисти.

*bAutoDestroy*<br/>
Означает, что объект будет уничтожен владельцем (pParentTarget).

## <a name="cd2dbrushdestroy"></a><a name="destroy"></a>CD2DBrush::Destroy

Уничтожает объект CD2DBrush.

```
virtual void Destroy();
```

## <a name="cd2dbrushdetach"></a><a name="detach"></a>CD2DBrush::Detach

Отсоединяет интерфейс ресурса с объекта.

```
ID2D1Brush* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на отдельный интерфейс ресурса.

## <a name="cd2dbrushget"></a><a name="get"></a>CD2DBrush::Get

Возвращает интерфейс ID2D1Brush

```
ID2D1Brush* Get();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1Brush или NULL, если объект еще не инициализирован.

## <a name="cd2dbrushgetopacity"></a><a name="getopacity"></a>CD2DBrush::GetOpacity

Получает степень непрозрачности этой кисти

```
FLOAT GetOpacity() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение между нулем и 1, что указывает на непрозрачность кисти. Это значение является постоянным множитель, который лирано масштабирует альфа-значение всех пикселей, заполненных кистью. Значения непрозрачности зажимаются в диапазоне от 0 до 1, прежде чем они умножаются вместе.

## <a name="cd2dbrushgettransform"></a><a name="gettransform"></a>CD2DBrush::GetTransform

Получает текущее преобразование цели рендеринга

```cpp
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;
```

### <a name="parameters"></a>Параметры

*Преобразования*<br/>
При возврате данных содержится текущее преобразование цели рендеринга. Этот параметр передается без инициализации.

## <a name="cd2dbrushisvalid"></a><a name="isvalid"></a>CD2DBrush::IsValid

Проверка достоверности ресурса

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если ресурс действителен; в противном случае FALSE.

## <a name="cd2dbrushm_pbrush"></a><a name="m_pbrush"></a>CD2DBrush::m_pBrush

Хранит указатель на объект ID2D1Brush.

```
ID2D1Brush* m_pBrush;
```

## <a name="cd2dbrushm_pbrushproperties"></a><a name="m_pbrushproperties"></a>CD2DBrush::m_pBrushProperties

Свойства кисти.

```
CD2DBrushProperties* m_pBrushProperties;
```

## <a name="cd2dbrushoperator-id2d1brush"></a><a name="operator_id2d1brush_star"></a>CD2DBrush::оператор ID2D1Brush

Возвращает интерфейс ID2D1Brush

```
operator ID2D1Brush*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1Brush или NULL, если объект еще не инициализирован.

## <a name="cd2dbrushsetopacity"></a><a name="setopacity"></a>CD2DBrush::SetOpacity

Устанавливает степень непрозрачности этой кисти

```cpp
void SetOpacity(FLOAT opacity);
```

### <a name="parameters"></a>Параметры

*Непрозрачность*<br/>
Значение между нулем и 1, что указывает на непрозрачность кисти. Это значение является постоянным множитель, который лирано масштабирует альфа-значение всех пикселей, заполненных кистью. Значения непрозрачности зажимаются в диапазоне от 0 до 1, прежде чем они умножаются вместе.

## <a name="cd2dbrushsettransform"></a><a name="settransform"></a>CD2DBrush::SetTransform

Применяет указанное преобразование к цели рендера, заменяя существующую трансформацию. Все последующие операции рисования происходят в преобразованном пространстве.

```cpp
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```

### <a name="parameters"></a>Параметры

*Преобразования*<br/>
Преобразование для применения к цели рендеринга

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
