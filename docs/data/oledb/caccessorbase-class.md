---
title: Класс CAccessorBase
ms.date: 11/04/2016
f1_keywords:
- CAccessorBase
- CAccessorBase.Close
- CAccessorBase::Close
- GetHAccessor
- CAccessorBase::GetHAccessor
- CAccessorBase.GetHAccessor
- CAccessorBase::GetNumAccessors
- GetNumAccessors
- CAccessorBase.GetNumAccessors
- IsAutoAccessor
- CAccessorBase.IsAutoAccessor
- CAccessorBase::IsAutoAccessor
- CAccessorBase::ReleaseAccessors
- CAccessorBase.ReleaseAccessors
- ReleaseAccessors
helpviewer_keywords:
- CAccessorBase class
- Close method
- GetHAccessor method
- GetNumAccessors method
- IsAutoAccessor method
- ReleaseAccessors method
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
ms.openlocfilehash: 5fb39d2291c2698dc57150eb44a6bbd6778812bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509312"
---
# <a name="caccessorbase-class"></a>Класс CAccessorBase

Все методы доступа в шаблонах OLE DB являются производными от этого класса. `CAccessorBase` позволяет одному набору строк для управления несколько методов доступа. Он также предоставляет привязки параметров и выходных столбцов.

## <a name="syntax"></a>Синтаксис

```cpp
// Replace with syntax
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[Закрыть](#close)|Закрывает методов доступа.|
|[GetHAccessor](#geth)|Извлекает дескриптор метода доступа.|
|[GetNumAccessors](#getnum)|Получает число методов доступа, созданный классом.|
|[IsAutoAccessor](#isauto)|Проверяет, является ли указанный метод доступа автоматическим.|
|[ReleaseAccessors](#release)|Освобождает методов доступа.|

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="close"></a> CAccessorBase::Close

Закрывает методов доступа.

### <a name="syntax"></a>Синтаксис

```cpp
void Close();
```

### <a name="remarks"></a>Примечания

Необходимо вызвать [ReleaseAccessors](../../data/oledb/caccessorbase-releaseaccessors.md) первого.

## <a name="geth"></a> CAccessorBase::GetHAccessor

Извлекает дескриптор метода доступа указанного метода доступа.

### <a name="syntax"></a>Синтаксис

```cpp
HACCESSOR GetHAccessor(ULONG nAccessor) const;
```

#### <a name="parameters"></a>Параметры

*nAccessor*<br/>
[in] Число ноль смещение для метода доступа.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор метода доступа.

## <a name="getnum"></a> CAccessorBase::GetNumAccessors

Получает число методов доступа, созданный классом.

### <a name="syntax"></a>Синтаксис

```cpp
ULONG GetNumAccessors() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число методов доступа, созданный классом.

## <a name="isauto"></a> CAccessorBase::IsAutoAccessor

Возвращает значение true, если данные извлекаются автоматически для метода доступа во время операции перемещения.

### <a name="syntax"></a>Синтаксис

```cpp
bool IsAutoAccessor(ULONG nAccessor) const;
```

#### <a name="parameters"></a>Параметры

*nAccessor*<br/>
[in] Число ноль смещение для метода доступа.

### <a name="return-value"></a>Возвращаемое значение

Возвращает **true** Если метод доступа является автоматическим. В противном случае возвращается значение **false**.

## <a name="release"></a> CAccessorBase::ReleaseAccessors

Освобождает методы доступа, созданный классом.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT ReleaseAccessors(IUnknown* pUnk);
```

#### <a name="parameters"></a>Параметры

*pUnk*<br/>
[in] Указатель на `IUnknown` интерфейса для COM-объекта, для которого будут созданы методы доступа.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Вызывается из [CAccessorRowset::Close](../../data/oledb/caccessorrowset-close.md).

## <a name="see-also"></a>См. также

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Класс CAccessorBase](../../data/oledb/caccessorbase-class.md)