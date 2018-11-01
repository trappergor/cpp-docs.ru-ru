---
title: Класс message_not_found
ms.date: 11/04/2016
f1_keywords:
- message_not_found
- CONCRT/concurrency::message_not_found
- CONCRT/concurrency::message_not_found::message_not_found
helpviewer_keywords:
- message_not_found class
ms.assetid: a96b9995-5ad7-4600-83c8-c15e329ff10e
ms.openlocfilehash: 7b6bd33e69d24e452414b2537ad70bf31e6b722f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458478"
---
# <a name="messagenotfound-class"></a>Класс message_not_found

Этот класс описывает исключение, создаваемое, когда блок обмена сообщениями не может найти запрошенное сообщение.

## <a name="syntax"></a>Синтаксис

```
class message_not_found : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[message_not_found](#ctor)|Перегружен. Создает объект `message_not_found`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`message_not_found`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> message_not_found

Создает объект `message_not_found`.

```
explicit _CRTIMP message_not_found(_In_z_ const char* _Message) throw();

message_not_found() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md)

