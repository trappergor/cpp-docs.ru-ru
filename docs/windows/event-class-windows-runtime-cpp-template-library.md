---
title: Класс событий (библиотека шаблонов C++ среды выполнения Windows) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event
dev_langs:
- C++
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c07d58f244bf2e7e6c9329196bae7b5bb323ce12
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644168"
---
# <a name="event-class-windows-runtime-c-template-library"></a>Класс Event (библиотека шаблонов C++ среды выполнения Windows)
Представляет событие.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
class Event : public HandleT<HandleTraits::EventTraits>;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор Event::Event (библиотека шаблонов C++ среды выполнения Windows)](../windows/event-event-constructor-windows-runtime-cpp-template-library.md)|Инициализирует новый экземпляр класса **событий** класса.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Оператор Event::operator=](../windows/event-operator-assign-operator.md)|Назначает указанное **событий** ссылку на текущий **событий** экземпляра.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `HandleT`  
  
 `Event`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)