---
title: Класс CD2DMesh
ms.date: 11/04/2016
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
ms.openlocfilehash: eaecdb6ba6f1382f16177e0567b31c9fd09da6ff
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753092"
---
# <a name="cd2dmesh-class"></a>Класс CD2DMesh

Обертка для ID2D1Mesh.

## <a name="syntax"></a>Синтаксис

```
class CD2DMesh : public CD2DResource;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DMesh::CD2DMesh](#cd2dmesh)|Строит объект CD2DMesh.|
|[CD2DMesh:: CD2DMesh](#_dtorcd2dmesh)|Деструктор Вызывается при уничтожении объекта сетки D2D.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DMesh:Attach](#attach)|Прикрепляет существующий интерфейс ресурса к объекту|
|[CD2DMesh::Создание](#create)|Создает CD2DMesh. (Переопределяет [CD2DРесурс::Создание](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DMesh: :Dэсстрой](#destroy)|Уничтожает объект CD2DMesh. (Переопределяет [CD2DРесурс::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DMesh::Detach](#detach)|Открепите интерфейс ресурса с объекта|
|[CD2DMesh::Get](#get)|Возвращает интерфейс ID2D1Mesh|
|[CD2DMesh::Действительно](#isvalid)|Проверка достоверности ресурса (Переопределения [CD2DРесурса:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DMesh::Открыто](#open)|Открывает сетку для населения.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DMesh:оператор ID2D1Mesh](#operator_id2d1mesh_star)|Возвращает интерфейс ID2D1Mesh|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CD2DMesh::m_pMesh](#m_pmesh)|Указатель на ID2D1Mesh.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DРесурс](../../mfc/reference/cd2dresource-class.md)

`CD2DMesh`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dmeshcd2dmesh"></a><a name="_dtorcd2dmesh"></a>CD2DMesh:: CD2DMesh

Деструктор Вызывается при уничтожении объекта сетки D2D.

```
virtual ~CD2DMesh();
```

## <a name="cd2dmeshattach"></a><a name="attach"></a>CD2DMesh:Attach

Прикрепляет существующий интерфейс ресурса к объекту

```cpp
void Attach(ID2D1Mesh* pResource);
```

### <a name="parameters"></a>Параметры

*pResource*<br/>
Существующий интерфейс ресурса. Не может быть NULL

## <a name="cd2dmeshcd2dmesh"></a><a name="cd2dmesh"></a>CD2DMesh::CD2DMesh

Строит объект CD2DMesh.

```
CD2DMesh(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*pParentTarget*<br/>
Указатель на цель рендера.

*bAutoDestroy*<br/>
Означает, что объект будет уничтожен владельцем (pParentTarget).

## <a name="cd2dmeshcreate"></a><a name="create"></a>CD2DMesh::Создание

Создает CD2DMesh.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Параметры

*pRenderTarget*<br/>
Указатель на цель рендера.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. В противном случае он возвращает код ошибки HRESULT.

## <a name="cd2dmeshdestroy"></a><a name="destroy"></a>CD2DMesh: :Dэсстрой

Уничтожает объект CD2DMesh.

```
virtual void Destroy();
```

## <a name="cd2dmeshdetach"></a><a name="detach"></a>CD2DMesh::Detach

Открепите интерфейс ресурса с объекта

```
ID2D1Mesh* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на отдельный интерфейс ресурса.

## <a name="cd2dmeshget"></a><a name="get"></a>CD2DMesh::Get

Возвращает интерфейс ID2D1Mesh

```
ID2D1Mesh* Get();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1Mesh или NULL, если объект еще не инициализирован.

## <a name="cd2dmeshisvalid"></a><a name="isvalid"></a>CD2DMesh::Действительно

Проверка достоверности ресурса

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если ресурс действителен; в противном случае FALSE.

## <a name="cd2dmeshm_pmesh"></a><a name="m_pmesh"></a>CD2DMesh::m_pMesh

Указатель на ID2D1Mesh.

```
ID2D1Mesh* m_pMesh;
```

## <a name="cd2dmeshopen"></a><a name="open"></a>CD2DMesh::Открыто

Открывает сетку для населения.

```
ID2D1TessellationSink* Open();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на ID2D1TessellationSSink, который используется для заполнения сетки.

## <a name="cd2dmeshoperator-id2d1mesh"></a><a name="operator_id2d1mesh_star"></a>CD2DMesh:оператор ID2D1Mesh

Возвращает интерфейс ID2D1Mesh

```
operator ID2D1Mesh*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1Mesh или NULL, если объект еще не инициализирован.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
