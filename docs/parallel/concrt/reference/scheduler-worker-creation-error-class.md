---
title: Класс scheduler_worker_creation_error
ms.date: 11/04/2016
f1_keywords:
- scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error::scheduler_worker_creation_error
helpviewer_keywords:
- scheduler_worker_creation_error class
ms.assetid: 4aec1c3e-c32a-41b2-899d-2d898f23b3c7
ms.openlocfilehash: 66e7485787606c22aba2970dbe481a7d29e66621
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268386"
---
# <a name="schedulerworkercreationerror-class"></a>Класс scheduler_worker_creation_error

Этот класс описывает исключение, которое создается из-за сбоя создания рабочего контекста выполнения в исполняющей среде с параллелизмом.

## <a name="syntax"></a>Синтаксис

```
class scheduler_worker_creation_error : public scheduler_resource_allocation_error;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[scheduler_worker_creation_error](#ctor)|Перегружен. Создает объект `scheduler_worker_creation_error`.|

## <a name="remarks"></a>Примечания

Это исключение обычно создается при сбое вызова, адресованного операционной системе, для создания контекста выполнения из исполняющей среды с параллелизмом. Контексты выполнения — это потоки, которые выполняют задачи исполняющей среды с параллелизмом. Код ошибки, который обычно возвращается из вызова метода Win32 `GetLastError`, преобразуется в значение типа `HRESULT` и может быть получен посредством метода базового класса `get_error_code`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

[scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)

`scheduler_worker_creation_error`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> scheduler_worker_creation_error

Создает объект `scheduler_worker_creation_error`.

```
scheduler_worker_creation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_worker_creation_error(
    HRESULT _Hresult) throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

*_Hresult*<br/>
`HRESULT` Значение ошибки, вызвавшей исключение.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
