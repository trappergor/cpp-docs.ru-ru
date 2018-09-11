---
title: Класс CComDynamicUnkArray | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::Add
- ATLCOM/ATL::CComDynamicUnkArray::begin
- ATLCOM/ATL::CComDynamicUnkArray::clear
- ATLCOM/ATL::CComDynamicUnkArray::end
- ATLCOM/ATL::CComDynamicUnkArray::GetAt
- ATLCOM/ATL::CComDynamicUnkArray::GetCookie
- ATLCOM/ATL::CComDynamicUnkArray::GetSize
- ATLCOM/ATL::CComDynamicUnkArray::GetUnknown
- ATLCOM/ATL::CComDynamicUnkArray::Remove
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71b36f19cc6e3deddbd5984e63b70c61a0ca8ea8
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762773"
---
# <a name="ccomdynamicunkarray-class"></a>Класс CComDynamicUnkArray

Этот класс содержит массив `IUnknown` указатели.

## <a name="syntax"></a>Синтаксис

```
class CComDynamicUnkArray
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|Конструктор. Инициализирует коллекцию значения NULL и размер коллекции до нуля.|
|[CComDynamicUnkArray:: ~ CComDynamicUnkArray](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComDynamicUnkArray::Add](#add)|Вызовите этот метод для добавления `IUnknown` указатель на массив.|
|[CComDynamicUnkArray::begin](#begin)|Возвращает указатель на первый `IUnknown` указатель в коллекции.|
|[CComDynamicUnkArray::clear](#clear)|Очищает массива.|
|[CComDynamicUnkArray::end](#end)|Возвращает указатель на позицию, следующую за последней `IUnknown` указатель в коллекции.|
|[CComDynamicUnkArray::GetAt](#getat)|Извлекает элемент по указанному индексу.|
|[CComDynamicUnkArray::GetCookie](#getcookie)|Вызовите этот метод, чтобы получить файл cookie, связанный с данной `IUnknown` указатель.|
|[CComDynamicUnkArray::GetSize](#getsize)|Возвращает длину массива.|
|[CComDynamicUnkArray::GetUnknown](#getunknown)|Вызовите этот метод для получения `IUnknown` указатель, связанный с заданным файлом cookie.|
|[CComDynamicUnkArray::Remove](#remove)|Вызовите этот метод для удаления `IUnknown` указатель из массива.|

## <a name="remarks"></a>Примечания

`CComDynamicUnkArray` содержит динамически выделяемого массива из `IUnknown` указатели, каждая точка интерфейс для подключения. `CComDynamicUnkArray` может использоваться в качестве параметра [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) класс шаблона.

`CComDynamicUnkArray` Методы [начать](#begin) и [окончания](#end) может использоваться для циклического прохождения через все точки подключения (например, когда происходит событие).

См. в разделе [Добавление точек подключения к объекту](../../atl/adding-connection-points-to-an-object.md) Дополнительные сведения об автоматизации создания подключения укажите учетные записи-посредники.

> [!NOTE]
> **Примечание** класса `CComDynamicUnkArray` используется **Добавление класса** мастер при создании элемента управления, который содержит точки подключения. Если вы хотите указать количество точек подключения вручную, измените ссылку с `CComDynamicUnkArray` для `CComUnkArray<` *n* `>`, где *n* — это число точек подключения Обязательно.

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="add"></a>  CComDynamicUnkArray::Add

Вызовите этот метод для добавления `IUnknown` указатель на массив.

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>Параметры

*pUnk*  
`IUnknown` Указатель, чтобы добавить в массив.

### <a name="return-value"></a>Возвращаемое значение

Возвращает файл cookie, связанный с вновь добавленный указатель.

##  <a name="begin"></a>  CComDynamicUnkArray::begin

Возвращает указатель на начало коллекции `IUnknown` указателей на интерфейс.

```
IUnknown**
    begin();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `IUnknown` указатель на интерфейс.

### <a name="remarks"></a>Примечания

Коллекция содержит указатели на интерфейсы, которые хранятся локально в виде `IUnknown`. Вы приводите каждый `IUnknown` интерфейса в тип real интерфейса и затем вызывать ее. Необходимо сначала запрашивать интерфейс.

Перед использованием `IUnknown` интерфейса, следует проверить, что он не равен NULL.

##  <a name="clear"></a>  CComDynamicUnkArray::clear

Очищает массива.

```
void clear();
```

##  <a name="ccomdynamicunkarray"></a>  CComDynamicUnkArray::CComDynamicUnkArray

Конструктор.

```
CComDynamicUnkArray();
```

### <a name="remarks"></a>Примечания

Задает размер коллекции равным нулю и инициализирует значения NULL. Деструктор освобождает коллекции, при необходимости.

##  <a name="dtor"></a>  CComDynamicUnkArray:: ~ CComDynamicUnkArray

Деструктор

```
~CComDynamicUnkArray();
```

### <a name="remarks"></a>Примечания

Освобождает ресурсы, выделенные с помощью конструктора класса.

##  <a name="end"></a>  CComDynamicUnkArray::end

Возвращает указатель на позицию, следующую за последней `IUnknown` указатель в коллекции.

```
IUnknown**
    end();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `IUnknown` указатель на интерфейс.

##  <a name="getat"></a>  CComDynamicUnkArray::GetAt

Извлекает элемент по указанному индексу.

```
IUnknown* GetAt(int nIndex);
```

### <a name="parameters"></a>Параметры

*nIndex*  
Индекс извлекаемого элемента.

### <a name="return-value"></a>Возвращаемое значение

Указатель на [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) интерфейс.

##  <a name="getcookie"></a>  CComDynamicUnkArray::GetCookie

Вызовите этот метод, чтобы получить файл cookie, связанный с данной `IUnknown` указатель.

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>Параметры

*ppFind*  
`IUnknown` Указатель, для которого необходим соответствующий файл cookie.

### <a name="return-value"></a>Возвращаемое значение

Возвращает файл cookie, связанный с `IUnknown` указателя, или нуль, если соответствующий `IUnknown` находится указатель.

### <a name="remarks"></a>Примечания

Если имеется несколько экземпляров одной и той же `IUnknown` указателем, эта функция возвращает файл cookie для первого из них.

##  <a name="getsize"></a>  CComDynamicUnkArray::GetSize

Возвращает длину массива.

```
int GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина массива.

##  <a name="getunknown"></a>  CComDynamicUnkArray::GetUnknown

Вызовите этот метод для получения `IUnknown` указатель, связанный с заданным файлом cookie.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>Параметры

*dwCookie*  
Файл cookie, для которого связанного `IUnknown` указатель является обязательным.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `IUnknown` указателя, или значение NULL, если нет соответствующий файл cookie найден.

##  <a name="remove"></a>  CComDynamicUnkArray::Remove

Вызовите этот метод для удаления `IUnknown` указатель из массива.

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>Параметры

*dwCookie*  
Ссылка на файл cookie `IUnknown` указатель, который необходимо удалить из массива.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если указатель удаляется; в противном случае — значение FALSE.

## <a name="see-also"></a>См. также

[Класс CComUnkArray](../../atl/reference/ccomunkarray-class.md)   
[Общие сведения о классе](../../atl/atl-class-overview.md)
