---
title: "Макрос Activatableclass | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ActivatableClass
- ActivatableClassWithFactory
- ActivatableClassWithFactoryEx
dev_langs:
- C++
helpviewer_keywords:
- ActivatableClassWithFactory
- ActivatableClass
- ActivatableClassWithFactoryEx
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7043a3a9013f02048b34149dd113d2125dced6a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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