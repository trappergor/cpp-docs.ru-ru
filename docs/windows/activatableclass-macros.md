---
title: "Макрос Activatableclass | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ActivatableClass
- ActivatableClassWithFactory
- ActivatableClassWithFactoryEx
dev_langs: C++
helpviewer_keywords:
- ActivatableClassWithFactory
- ActivatableClass
- ActivatableClassWithFactoryEx
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6cd75d4075cfe590151f7746281640febb334ce9
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="activatableclass-macros"></a>Макрос ActivatableClass

Заполняет внутренний кэш, который содержит фабрику, можно создать экземпляр указанного класса.

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

*className*  
Имя для создаваемого класса.  

*фабрики*  
Фабрика, которая создает экземпляр указанного класса.

*Имя сервера*  
Имя, которое определяет подмножество фабрики в модуле.

## <a name="remarks"></a>Примечания

Не используйте эти макросы классической модели COM, если вы не используете `#undef` директиву, чтобы убедиться, что **&#95; &#95; WRL_WINRT_STRICT &#95; &#95;**  удаляется определение макроса.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс Module](../windows/module-class.md)