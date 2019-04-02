---
title: Макрос ActivatableClass
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ActivatableClass
- ActivatableClassWithFactory
- ActivatableClassWithFactoryEx
helpviewer_keywords:
- ActivatableClassWithFactory
- ActivatableClass
- ActivatableClassWithFactoryEx
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
ms.openlocfilehash: eee8267e2e76eead267eb2486836dbcc38a90231
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785968"
---
# <a name="activatableclass-macros"></a>Макрос ActivatableClass

Заполняет внутренний кэш, содержащий фабрику, можно создать экземпляр указанного класса.

## <a name="syntax"></a>Синтаксис

```cpp
ActivatableClass(
   className
);

ActivatableClassWithFactory(
   className,
   factory
);

ActivatableClassWithFactoryEx(
   className,
   factory,
   serverName
);
```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя создаваемого класса.

*фабрики*<br/>
Фабрика, которая будет создавать экземпляр указанного класса.

*Имя_сервера*<br/>
Имя, которое определяет подмножество фабрики в модуле.

## <a name="remarks"></a>Примечания

Не используйте эти макросы с помощью классической COM, если вы не используете `#undef` директиву, чтобы убедиться, что `__WRL_WINRT_STRICT__` удаляется определение макроса.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс Module](module-class.md)