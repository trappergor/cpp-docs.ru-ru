---
title: Класс CD2DLayer
ms.date: 11/04/2016
f1_keywords:
- CD2DLayer
- AFXRENDERTARGET/CD2DLayer
- AFXRENDERTARGET/CD2DLayer::CD2DLayer
- AFXRENDERTARGET/CD2DLayer::Attach
- AFXRENDERTARGET/CD2DLayer::Create
- AFXRENDERTARGET/CD2DLayer::Destroy
- AFXRENDERTARGET/CD2DLayer::Detach
- AFXRENDERTARGET/CD2DLayer::Get
- AFXRENDERTARGET/CD2DLayer::GetSize
- AFXRENDERTARGET/CD2DLayer::IsValid
- AFXRENDERTARGET/CD2DLayer::m_pLayer
helpviewer_keywords:
- CD2DLayer [MFC], CD2DLayer
- CD2DLayer [MFC], Attach
- CD2DLayer [MFC], Create
- CD2DLayer [MFC], Destroy
- CD2DLayer [MFC], Detach
- CD2DLayer [MFC], Get
- CD2DLayer [MFC], GetSize
- CD2DLayer [MFC], IsValid
- CD2DLayer [MFC], m_pLayer
ms.assetid: 2f96378e-66bb-40d1-9661-6afe324de3c1
ms.openlocfilehash: cd4452eeb9e600aeabaec1b54fd40217514e02eb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531720"
---
# <a name="cd2dlayer-class"></a>Класс CD2DLayer

Оболочка для ID2D1Layer.

## <a name="syntax"></a>Синтаксис

```
class CD2DLayer : public CD2DResource;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DLayer::CD2DLayer](#cd2dlayer)|Создает объект CD2DLayer.|
|[CD2DLayer:: ~ CD2DLayer](#_dtorcd2dlayer)|Деструктор Вызывается при уничтожении объекта D2D слоя.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DLayer::Attach](#attach)|Присоединяет существующий интерфейс ресурса к объекту|
|[CD2DLayer::CREATE](#create)|Создает CD2DLayer. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DLayer::destroy](#destroy)|Уничтожает объект CD2DLayer. (Переопределяет [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DLayer::Detach](#detach)|Отсоединяет интерфейс ресурса из объекта|
|[CD2DLayer::Get](#get)|Возвращает интерфейс ID2D1Layer|
|[CD2DLayer::GetSize](#getsize)|Возвращает размер целевого объекта отрисовки в аппаратно независимых пикселей|
|[CD2DLayer::IsValid](#isvalid)|Проверяет допустимость ресурсов (переопределяет [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DLayer::operator ID2D1Layer *](#operator_id2d1layer_star)|Возвращает интерфейс ID2D1Layer|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CD2DLayer::m_pLayer](#m_player)|Содержит указатель на объект ID2D1Layer.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DLayer`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

##  <a name="_dtorcd2dlayer"></a>  CD2DLayer:: ~ CD2DLayer

Деструктор Вызывается при уничтожении объекта D2D слоя.

```
virtual ~CD2DLayer();
```

##  <a name="attach"></a>  CD2DLayer::Attach

Присоединяет существующий интерфейс ресурса к объекту

```
void Attach(ID2D1Layer* pResource);
```

### <a name="parameters"></a>Параметры

*pResource*<br/>
Существующий интерфейс ресурсов. Не может иметь значение NULL

##  <a name="cd2dlayer"></a>  CD2DLayer::CD2DLayer

Создает объект CD2DLayer.

```
CD2DLayer(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*pParentTarget*<br/>
Указатель на целевой объект отрисовки.

*bAutoDestroy*<br/>
Указывает, что объект будет уничтожен владельца (pParentTarget).

##  <a name="create"></a>  CD2DLayer::CREATE

Создает CD2DLayer.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Параметры

*pRenderTarget*<br/>
Указатель на целевой объект отрисовки.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. В противном случае он возвращает код ошибки HRESULT.

##  <a name="destroy"></a>  CD2DLayer::destroy

Уничтожает объект CD2DLayer.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DLayer::Detach

Отсоединяет интерфейс ресурса из объекта

```
ID2D1Layer* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс отсоединенных ресурсов.

##  <a name="get"></a>  CD2DLayer::Get

Возвращает интерфейс ID2D1Layer

```
ID2D1Layer* Get();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1Layer или значение NULL, если объект еще не инициализирован.

##  <a name="getsize"></a>  CD2DLayer::GetSize

Возвращает размер целевого объекта отрисовки в аппаратно независимых пикселей

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий размер целевого объекта отрисовки в аппаратно независимых пикселях

##  <a name="isvalid"></a>  CD2DLayer::IsValid

Проверяет допустимость ресурсов

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если ресурс является допустимым; в противном случае — значение FALSE.

##  <a name="m_player"></a>  CD2DLayer::m_pLayer

Содержит указатель на объект ID2D1Layer.

```
ID2D1Layer* m_pLayer;
```

##  <a name="operator_id2d1layer_star"></a>  CD2DLayer::operator ID2D1Layer *

Возвращает интерфейс ID2D1Layer

```
operator ID2D1Layer* ();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1Layer или значение NULL, если объект еще не инициализирован.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
