---
title: Класс Ккомдинамикункаррай
ms.date: 11/04/2016
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
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
ms.openlocfilehash: d55a6d6bfbcc6921fa0633753365f5799388dc27
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497257"
---
# <a name="ccomdynamicunkarray-class"></a>Класс Ккомдинамикункаррай

Этот класс хранит массив `IUnknown` указателей.

## <a name="syntax"></a>Синтаксис

```
class CComDynamicUnkArray
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Ккомдинамикункаррай:: Ккомдинамикункаррай](#ccomdynamicunkarray)|Конструктор. Инициализирует значения коллекции значением NULL, а размер коллекции — нулем.|
|[Ккомдинамикункаррай:: ~ Ккомдинамикункаррай](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Ккомдинамикункаррай:: Add](#add)|Вызовите этот метод, чтобы `IUnknown` добавить указатель на массив.|
|[Ккомдинамикункаррай:: Begin](#begin)|Возвращает указатель на первый `IUnknown` указатель в коллекции.|
|[Ккомдинамикункаррай:: Clear](#clear)|Очищает массив.|
|[Ккомдинамикункаррай:: end](#end)|Возвращает указатель на один `IUnknown` из последних указателей в коллекции.|
|[Ккомдинамикункаррай:: GetAt](#getat)|Извлекает элемент по указанному индексу.|
|[Ккомдинамикункаррай:: Кука](#getcookie)|Вызовите этот метод, чтобы получить файл cookie, связанный `IUnknown` с заданным указателем.|
|[Ккомдинамикункаррай:: DataSize](#getsize)|Возвращает длину массива.|
|[Ккомдинамикункаррай:: неизвестный](#getunknown)|Вызовите этот метод, чтобы `IUnknown` получить указатель, связанный с заданным файлом cookie.|
|[Ккомдинамикункаррай:: Remove](#remove)|Вызовите этот метод, чтобы `IUnknown` удалить указатель из массива.|

## <a name="remarks"></a>Примечания

`CComDynamicUnkArray`содержит динамически выделенный массив `IUnknown` указателей, каждый из которых является интерфейсом в точке соединения. `CComDynamicUnkArray`может использоваться в качестве параметра для класса шаблона [иконнектионпоинтимпл](../../atl/reference/iconnectionpointimpl-class.md) .

`CComDynamicUnkArray` Методы [Begin](#begin) и [End](#end) можно использовать для выполнения цикла по всем точкам соединения (например, при срабатывании события).

Дополнительные сведения об автоматизации создания прокси-серверов точек подключения см. в разделе [Добавление точек подключения к объекту](../../atl/adding-connection-points-to-an-object.md) .

> [!NOTE]
> **Примечание** . Класс `CComDynamicUnkArray` используется мастером **добавления классов** при создании элемента управления с точками соединения. Если вы хотите вручную указать число точек соединения `CComDynamicUnkArray` , измените ссылку с на `>` `CComUnkArray<` n, где *n* — необходимое число точек соединения.

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="add"></a>Ккомдинамикункаррай:: Add

Вызовите этот метод, чтобы `IUnknown` добавить указатель на массив.

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>Параметры

*pUnk*<br/>
`IUnknown` Указатель, добавляемый в массив.

### <a name="return-value"></a>Возвращаемое значение

Возвращает файл cookie, связанный с вновь добавленным указателем.

##  <a name="begin"></a>Ккомдинамикункаррай:: Begin

Возвращает указатель на начало коллекции `IUnknown` указателей интерфейса.

```
IUnknown**
    begin();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `IUnknown` указатель интерфейса.

### <a name="remarks"></a>Примечания

Коллекция содержит указатели на интерфейсы, хранимые `IUnknown`локально как. Каждый `IUnknown` интерфейс приводится к реальному типу интерфейса, а затем вызывается через него. Сначала не нужно запрашивать интерфейс.

Прежде чем использовать `IUnknown` интерфейс, убедитесь, что он не равен null.

##  <a name="clear"></a>Ккомдинамикункаррай:: Clear

Очищает массив.

```
void clear();
```

##  <a name="ccomdynamicunkarray"></a>Ккомдинамикункаррай:: Ккомдинамикункаррай

Конструктор.

```
CComDynamicUnkArray();
```

### <a name="remarks"></a>Примечания

Устанавливает нулевой размер коллекции и инициализирует значения значением NULL. При необходимости Деструктор освобождает коллекцию.

##  <a name="dtor"></a>Ккомдинамикункаррай:: ~ Ккомдинамикункаррай

Деструктор

```
~CComDynamicUnkArray();
```

### <a name="remarks"></a>Примечания

Освобождает ресурсы, выделенные конструктором класса.

##  <a name="end"></a>Ккомдинамикункаррай:: end

Возвращает указатель на один `IUnknown` из последних указателей в коллекции.

```
IUnknown**
    end();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `IUnknown` указатель интерфейса.

##  <a name="getat"></a>Ккомдинамикункаррай:: GetAt

Извлекает элемент по указанному индексу.

```
IUnknown* GetAt(int nIndex);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Индекс извлекаемого элемента.

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) .

##  <a name="getcookie"></a>Ккомдинамикункаррай:: Кука

Вызовите этот метод, чтобы получить файл cookie, связанный `IUnknown` с заданным указателем.

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>Параметры

*ппфинд*<br/>
`IUnknown` Указатель, для которого требуется связанный файл cookie.

### <a name="return-value"></a>Возвращаемое значение

Возвращает файл cookie, связанный с `IUnknown` указателем, или нуль, если `IUnknown` соответствующий указатель не найден.

### <a name="remarks"></a>Примечания

Если имеется несколько экземпляров одного и того же `IUnknown` указателя, эта функция возвращает файл cookie для первого объекта.

##  <a name="getsize"></a>Ккомдинамикункаррай:: DataSize

Возвращает длину массива.

```
int GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина массива.

##  <a name="getunknown"></a>Ккомдинамикункаррай:: неизвестный

Вызовите этот метод, чтобы `IUnknown` получить указатель, связанный с заданным файлом cookie.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>Параметры

*двкукие*<br/>
Файл cookie, для которого требуется `IUnknown` связанный указатель.

### <a name="return-value"></a>Возвращаемое значение

`IUnknown` Возвращает указатель или значение null, если соответствующий файл cookie не найден.

##  <a name="remove"></a>Ккомдинамикункаррай:: Remove

Вызовите этот метод, чтобы `IUnknown` удалить указатель из массива.

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>Параметры

*двкукие*<br/>
Файл cookie, ссылающийся `IUnknown` на указатель, удаляемый из массива.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если указатель удален; в противном случае — FALSE.

## <a name="see-also"></a>См. также

[Класс CComUnkArray](../../atl/reference/ccomunkarray-class.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
