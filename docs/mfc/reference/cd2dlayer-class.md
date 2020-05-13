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
ms.openlocfilehash: 30025d6097e439c07202d144a6e549845b78ffa6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754756"
---
# <a name="cd2dlayer-class"></a>Класс CD2DLayer

Обертка для ID2D1Layer.

## <a name="syntax"></a>Синтаксис

```
class CD2DLayer : public CD2DResource;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DLayer::CD2DLayer](#cd2dlayer)|Строит объект CD2DLayer.|
|[CD2DLayer:::CD2DLayer](#_dtorcd2dlayer)|Деструктор Вызывается при уничтожении объекта слоя D2D.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DLayer::Прикрепите](#attach)|Прикрепляет существующий интерфейс ресурса к объекту|
|[CD2DLayer::Создание](#create)|Создает CD2DLayer. (Переопределяет [CD2DРесурс::Создание](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DLayer::Dэсстрой](#destroy)|Уничтожает объект CD2DLayer. (Переопределяет [CD2DРесурс::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DLayer::Detach](#detach)|Открепите интерфейс ресурса с объекта|
|[CD2DLayer::Получить](#get)|Возвращает интерфейс ID2D1Layer|
|[CD2DLayer::GetSize](#getsize)|Возвращает размер цели рендеринга в независях от устройства пикселей|
|[CD2DLayer::Действительно](#isvalid)|Проверка достоверности ресурса (Переопределения [CD2DРесурса:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DLayer:Оператор ID2D1Layer](#operator_id2d1layer_star)|Возвращает интерфейс ID2D1Layer|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CD2DLayer::m_pLayer](#m_player)|Хранит указатель на объект ID2D1Layer.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DРесурс](../../mfc/reference/cd2dresource-class.md)

`CD2DLayer`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dlayercd2dlayer"></a><a name="_dtorcd2dlayer"></a>CD2DLayer:::CD2DLayer

Деструктор Вызывается при уничтожении объекта слоя D2D.

```
virtual ~CD2DLayer();
```

## <a name="cd2dlayerattach"></a><a name="attach"></a>CD2DLayer::Прикрепите

Прикрепляет существующий интерфейс ресурса к объекту

```cpp
void Attach(ID2D1Layer* pResource);
```

### <a name="parameters"></a>Параметры

*pResource*<br/>
Существующий интерфейс ресурса. Не может быть NULL

## <a name="cd2dlayercd2dlayer"></a><a name="cd2dlayer"></a>CD2DLayer::CD2DLayer

Строит объект CD2DLayer.

```
CD2DLayer(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*pParentTarget*<br/>
Указатель на цель рендера.

*bAutoDestroy*<br/>
Означает, что объект будет уничтожен владельцем (pParentTarget).

## <a name="cd2dlayercreate"></a><a name="create"></a>CD2DLayer::Создание

Создает CD2DLayer.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Параметры

*pRenderTarget*<br/>
Указатель на цель рендера.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. В противном случае он возвращает код ошибки HRESULT.

## <a name="cd2dlayerdestroy"></a><a name="destroy"></a>CD2DLayer::Dэсстрой

Уничтожает объект CD2DLayer.

```
virtual void Destroy();
```

## <a name="cd2dlayerdetach"></a><a name="detach"></a>CD2DLayer::Detach

Открепите интерфейс ресурса с объекта

```
ID2D1Layer* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на отдельный интерфейс ресурса.

## <a name="cd2dlayerget"></a><a name="get"></a>CD2DLayer::Получить

Возвращает интерфейс ID2D1Layer

```
ID2D1Layer* Get();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1Layer или NULL, если объект еще не инициализирован.

## <a name="cd2dlayergetsize"></a><a name="getsize"></a>CD2DLayer::GetSize

Возвращает размер цели рендеринга в независях от устройства пикселей

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий размер цели рендеринга в независях от устройства пикселей

## <a name="cd2dlayerisvalid"></a><a name="isvalid"></a>CD2DLayer::Действительно

Проверка достоверности ресурса

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если ресурс действителен; в противном случае FALSE.

## <a name="cd2dlayerm_player"></a><a name="m_player"></a>CD2DLayer::m_pLayer

Хранит указатель на объект ID2D1Layer.

```
ID2D1Layer* m_pLayer;
```

## <a name="cd2dlayeroperator-id2d1layer"></a><a name="operator_id2d1layer_star"></a>CD2DLayer:Оператор ID2D1Layer

Возвращает интерфейс ID2D1Layer

```
operator ID2D1Layer* ();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1Layer или NULL, если объект еще не инициализирован.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
