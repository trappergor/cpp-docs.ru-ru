---
title: Класс bad_target
ms.date: 11/04/2016
f1_keywords:
- bad_target
- CONCRT/concurrency::bad_target
- CONCRT/concurrency::bad_target::bad_target
helpviewer_keywords:
- bad_target class
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
ms.openlocfilehash: 0440955718bee3b426f5e4625b5eb3fc559a5d28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434487"
---
# <a name="badtarget-class"></a>Класс bad_target

Этот класс описывает исключение, которое создается, если блок обмена сообщениями получает указатель на целевой объект, который неверен для выполняемой операции.

## <a name="syntax"></a>Синтаксис

```
class bad_target : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[bad_target](#ctor)|Перегружен. Создает объект `bad_target`.|

## <a name="remarks"></a>Примечания

Это исключение обычно вызывается по причинам, например попытка получить сообщение, которое зарезервировано для другой целевой объект или освобождение резервирование, которое не содержит целевого объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`bad_target`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> bad_target

Создает объект `bad_target`.

```
explicit _CRTIMP bad_target(_In_z_ const char* _Message) throw();

bad_target() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md)

