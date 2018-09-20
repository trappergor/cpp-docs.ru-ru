---
title: Класс CD2DMesh | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DMesh
- AFXRENDERTARGET/CD2DMesh
- AFXRENDERTARGET/CD2DMesh::CD2DMesh
- AFXRENDERTARGET/CD2DMesh::Attach
- AFXRENDERTARGET/CD2DMesh::Create
- AFXRENDERTARGET/CD2DMesh::Destroy
- AFXRENDERTARGET/CD2DMesh::Detach
- AFXRENDERTARGET/CD2DMesh::Get
- AFXRENDERTARGET/CD2DMesh::IsValid
- AFXRENDERTARGET/CD2DMesh::Open
- AFXRENDERTARGET/CD2DMesh::m_pMesh
dev_langs:
- C++
helpviewer_keywords:
- CD2DMesh [MFC], CD2DMesh
- CD2DMesh [MFC], Attach
- CD2DMesh [MFC], Create
- CD2DMesh [MFC], Destroy
- CD2DMesh [MFC], Detach
- CD2DMesh [MFC], Get
- CD2DMesh [MFC], IsValid
- CD2DMesh [MFC], Open
- CD2DMesh [MFC], m_pMesh
ms.assetid: 11a2c78a-1367-40e8-a34f-44aa0509a4c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7ed748a7f098dcbec68decbff29f8973e0b8476
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405987"
---
# <a name="cd2dmesh-class"></a>Класс CD2DMesh

Оболочка для ID2D1Mesh.

## <a name="syntax"></a>Синтаксис

```
class CD2DMesh : public CD2DResource;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DMesh::CD2DMesh](#cd2dmesh)|Создает объект CD2DMesh.|
|[CD2DMesh:: ~ CD2DMesh](#_dtorcd2dmesh)|Деструктор Вызывается при уничтожении объекта D2D сетки.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DMesh::Attach](#attach)|Присоединяет существующий интерфейс ресурса к объекту|
|[CD2DMesh::CREATE](#create)|Создает CD2DMesh. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DMesh::destroy](#destroy)|Уничтожает объект CD2DMesh. (Переопределяет [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DMesh::Detach](#detach)|Отсоединяет интерфейс ресурса из объекта|
|[CD2DMesh::Get](#get)|Возвращает интерфейс ID2D1Mesh|
|[CD2DMesh::IsValid](#isvalid)|Проверяет допустимость ресурсов (переопределяет [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DMesh::Open](#open)|Открывает сетку для заполнения.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DMesh::operator ID2D1Mesh *](#operator_id2d1mesh_star)|Возвращает интерфейс ID2D1Mesh|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CD2DMesh::m_pMesh](#m_pmesh)|Указатель на ID2D1Mesh.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DMesh`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

##  <a name="_dtorcd2dmesh"></a>  CD2DMesh:: ~ CD2DMesh

Деструктор Вызывается при уничтожении объекта D2D сетки.

```
virtual ~CD2DMesh();
```

##  <a name="attach"></a>  CD2DMesh::Attach

Присоединяет существующий интерфейс ресурса к объекту

```
void Attach(ID2D1Mesh* pResource);
```

### <a name="parameters"></a>Параметры

*pResource*<br/>
Существующий интерфейс ресурсов. Не может иметь значение NULL

##  <a name="cd2dmesh"></a>  CD2DMesh::CD2DMesh

Создает объект CD2DMesh.

```
CD2DMesh(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*pParentTarget*<br/>
Указатель на целевой объект отрисовки.

*bAutoDestroy*<br/>
Указывает, что объект будет уничтожен владельца (pParentTarget).

##  <a name="create"></a>  CD2DMesh::CREATE

Создает CD2DMesh.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Параметры

*pRenderTarget*<br/>
Указатель на целевой объект отрисовки.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. В противном случае он возвращает код ошибки HRESULT.

##  <a name="destroy"></a>  CD2DMesh::destroy

Уничтожает объект CD2DMesh.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DMesh::Detach

Отсоединяет интерфейс ресурса из объекта

```
ID2D1Mesh* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс отсоединенных ресурсов.

##  <a name="get"></a>  CD2DMesh::Get

Возвращает интерфейс ID2D1Mesh

```
ID2D1Mesh* Get();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1Mesh или значение NULL, если объект еще не инициализирован.

##  <a name="isvalid"></a>  CD2DMesh::IsValid

Проверяет допустимость ресурсов

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если ресурс является допустимым; в противном случае — значение FALSE.

##  <a name="m_pmesh"></a>  CD2DMesh::m_pMesh

Указатель на ID2D1Mesh.

```
ID2D1Mesh* m_pMesh;
```

##  <a name="open"></a>  CD2DMesh::Open

Открывает сетку для заполнения.

```
ID2D1TessellationSink* Open();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на ID2D1TessellationSink, который используется для заполнения сетки.

##  <a name="operator_id2d1mesh_star"></a>  CD2DMesh::operator ID2D1Mesh *

Возвращает интерфейс ID2D1Mesh

```
operator ID2D1Mesh*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1Mesh или значение NULL, если объект еще не инициализирован.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
