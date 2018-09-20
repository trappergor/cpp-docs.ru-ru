---
title: Класс CD2DPathGeometry | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::Attach
- AFXRENDERTARGET/CD2DPathGeometry::Create
- AFXRENDERTARGET/CD2DPathGeometry::Destroy
- AFXRENDERTARGET/CD2DPathGeometry::Detach
- AFXRENDERTARGET/CD2DPathGeometry::GetFigureCount
- AFXRENDERTARGET/CD2DPathGeometry::GetSegmentCount
- AFXRENDERTARGET/CD2DPathGeometry::Open
- AFXRENDERTARGET/CD2DPathGeometry::Stream
- AFXRENDERTARGET/CD2DPathGeometry::m_pPathGeometry
dev_langs:
- C++
helpviewer_keywords:
- CD2DPathGeometry [MFC], CD2DPathGeometry
- CD2DPathGeometry [MFC], Attach
- CD2DPathGeometry [MFC], Create
- CD2DPathGeometry [MFC], Destroy
- CD2DPathGeometry [MFC], Detach
- CD2DPathGeometry [MFC], GetFigureCount
- CD2DPathGeometry [MFC], GetSegmentCount
- CD2DPathGeometry [MFC], Open
- CD2DPathGeometry [MFC], Stream
- CD2DPathGeometry [MFC], m_pPathGeometry
ms.assetid: 686216eb-5080-4242-ace5-8fa1ce96307c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 80d4116d71eb92474675968e15846f109b7390f0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388853"
---
# <a name="cd2dpathgeometry-class"></a>Класс CD2DPathGeometry

Оболочка для ID2D1PathGeometry.

## <a name="syntax"></a>Синтаксис

```
class CD2DPathGeometry : public CD2DGeometry;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DPathGeometry::CD2DPathGeometry](#cd2dpathgeometry)|Создает объект CD2DPathGeometry.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DPathGeometry::Attach](#attach)|Присоединяет существующий интерфейс ресурса к объекту|
|[CD2DPathGeometry::CREATE](#create)|Создает CD2DPathGeometry. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DPathGeometry::destroy](#destroy)|Уничтожает объект CD2DPathGeometry. (Переопределяет [CD2DGeometry::Destroy](../../mfc/reference/cd2dgeometry-class.md#destroy).)|
|[CD2DPathGeometry::Detach](#detach)|Отсоединяет интерфейс ресурса из объекта|
|[CD2DPathGeometry::GetFigureCount](#getfigurecount)|Получает число фигур геометрическому пути.|
|[CD2DPathGeometry::GetSegmentCount](#getsegmentcount)|Возвращает число сегментов в по геометрическому пути.|
|[CD2DPathGeometry::Open](#open)|Получает приемник geometry, который используется для заполнения по геометрическому пути с цифры и сегментами.|
|[CD2DPathGeometry::Stream](#stream)|Копирует содержимое по геометрическому пути к указанным ID2D1GeometrySink.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CD2DPathGeometry::m_pPathGeometry](#m_ppathgeometry)|Указатель на ID2D1PathGeometry.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DGeometry](../../mfc/reference/cd2dgeometry-class.md)

`CD2DPathGeometry`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

##  <a name="attach"></a>  CD2DPathGeometry::Attach

Присоединяет существующий интерфейс ресурса к объекту

```
void Attach(ID2D1PathGeometry* pResource);
```

### <a name="parameters"></a>Параметры

*pResource*<br/>
Существующий интерфейс ресурсов. Не может иметь значение NULL

##  <a name="cd2dpathgeometry"></a>  CD2DPathGeometry::CD2DPathGeometry

Создает объект CD2DPathGeometry.

```
CD2DPathGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*pParentTarget*<br/>
Указатель на целевой объект отрисовки.

*bAutoDestroy*<br/>
Указывает, что объект будет уничтожен владельца (pParentTarget).

##  <a name="create"></a>  CD2DPathGeometry::CREATE

Создает CD2DPathGeometry.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Параметры

*pRenderTarget*<br/>
Указатель на целевой объект отрисовки.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. В противном случае он возвращает код ошибки HRESULT.

##  <a name="destroy"></a>  CD2DPathGeometry::destroy

Уничтожает объект CD2DPathGeometry.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DPathGeometry::Detach

Отсоединяет интерфейс ресурса из объекта

```
ID2D1PathGeometry* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс отсоединенных ресурсов.

##  <a name="getfigurecount"></a>  CD2DPathGeometry::GetFigureCount

Получает число фигур геометрическому пути.

```
int GetFigureCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает число фигур в по геометрическому пути.

##  <a name="getsegmentcount"></a>  CD2DPathGeometry::GetSegmentCount

Возвращает число сегментов в по геометрическому пути.

```
int GetSegmentCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает число сегментов в по геометрическому пути.

##  <a name="m_ppathgeometry"></a>  CD2DPathGeometry::m_pPathGeometry

Указатель на ID2D1PathGeometry.

```
ID2D1PathGeometry* m_pPathGeometry;
```

##  <a name="open"></a>  CD2DPathGeometry::Open

Получает приемник geometry, который используется для заполнения по геометрическому пути с цифры и сегментами.

```
ID2D1GeometrySink* Open();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на ID2D1GeometrySink, используемый для заполнения по геометрическому пути с цифры и сегментами.

##  <a name="stream"></a>  CD2DPathGeometry::Stream

Копирует содержимое по геометрическому пути к указанным ID2D1GeometrySink.

```
BOOL Stream(ID2D1GeometrySink* geometrySink);
```

### <a name="parameters"></a>Параметры

*geometrySink*<br/>
Приемник, в которой будет скопировано содержимое по геометрическому пути. Изменив этот приемник не изменяет содержимое данной геометрии пути.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
