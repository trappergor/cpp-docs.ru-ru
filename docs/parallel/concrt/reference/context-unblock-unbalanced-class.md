---
title: Класс context_unblock_unbalanced
ms.date: 11/04/2016
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
ms.openlocfilehash: f4f385cde2a27665afa5eb9869eb52bc42c70111
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283999"
---
# <a name="contextunblockunbalanced-class"></a>Класс context_unblock_unbalanced

Данный класс описывает исключение, создаваемое, если вызовы методов `Block` и `Unblock` объекта `Context` объединены неправильно.

## <a name="syntax"></a>Синтаксис

```
class context_unblock_unbalanced : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[context_unblock_unbalanced](#ctor)|Перегружен. Создает объект `context_unblock_unbalanced`.|

## <a name="remarks"></a>Примечания

Вызовы `Block` и `Unblock` методы `Context` объект должен всегда быть правильно пару. Среда выполнения с параллелизмом позволяет операциям происходить в любом порядке. Например, за вызовом `Block` может следовать вызов `Unblock`, или наоборот. Это исключение выдается, если, например, два вызова к `Unblock` метод были сделаны в строке, на `Context` объект, который не был заблокирован.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`context_unblock_unbalanced`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> context_unblock_unbalanced

Создает объект `context_unblock_unbalanced`.

```
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

context_unblock_unbalanced() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
