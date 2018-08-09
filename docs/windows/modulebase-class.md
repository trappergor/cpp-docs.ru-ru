---
title: Класс ModuleBase | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase
dev_langs:
- C++
helpviewer_keywords:
- ModuleBase class
ms.assetid: edce7591-6893-46f7-94a7-382827775548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8ff7fb86b7b39e283c27ee78611444b78bc53c5b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020282"
---
# <a name="modulebase-class"></a>Класс ModuleBase
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
class ModuleBase;  
```  
  
## <a name="remarks"></a>Примечания  
 Представляет базовый класс для [модуль](../windows/module-class.md) классы.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор ModuleBase::ModuleBase](../windows/modulebase-modulebase-constructor.md)|Инициализирует экземпляр класса `Module`.|  
|[Деструктор ModuleBase::~ModuleBase](../windows/modulebase-tilde-modulebase-destructor.md)|Деинициализирует текущий экземпляр `Module` класса.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод ModuleBase::DecrementObjectCount](../windows/modulebase-decrementobjectcount-method.md)|При реализации уменьшает число объектов, отслеживаемых модулем.|  
|[Метод ModuleBase::IncrementObjectCount](../windows/modulebase-incrementobjectcount-method.md)|При реализации увеличивает число объектов, отслеживаемых модулем.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ModuleBase`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)