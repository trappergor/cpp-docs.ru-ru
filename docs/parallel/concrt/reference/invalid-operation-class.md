---
title: Класс invalid_operation
ms.date: 11/04/2016
f1_keywords:
- invalid_operation
- CONCRT/concurrency::invalid_operation
- CONCRT/concurrency::invalid_operation::invalid_operation
helpviewer_keywords:
- invalid_operation class
ms.assetid: 26ba07dc-fcdf-44cb-b748-a31d35205b52
ms.openlocfilehash: 8b971a12ff83753546cfea7b90288d1bc43400c0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57279693"
---
# <a name="invalidoperation-class"></a>Класс invalid_operation

Данный класс описывает исключение, возникающее при выполнении недопустимой операции, которая не описывается более точно другим типом исключения, создаваемым средой выполнения с параллелизмом.

## <a name="syntax"></a>Синтаксис

```
class invalid_operation : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[invalid_operation](#ctor)|Перегружен. Создает объект `invalid_operation`.|

## <a name="remarks"></a>Примечания

Различные методы, создающие это исключение, обычно документируют, в каких обстоятельствах они создают его.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`invalid_operation`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> invalid_operation

Создает объект `invalid_operation`.

```
explicit _CRTIMP invalid_operation(_In_z_ const char* _Message) throw();

invalid_operation() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
