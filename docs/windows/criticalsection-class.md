---
title: Criticalsection-класс | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CriticalSection class
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b65ded3ae56eb1d57bad771a8875cce4948d2953
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642099"
---
# <a name="criticalsection-class"></a>CriticalSection - класс
Представляет объект критической секции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
class CriticalSection;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="constructor"></a>Конструктор  
  
|name|Описание:|  
|----------|-----------------|  
|[Конструктор CriticalSection::CriticalSection](../windows/criticalsection-criticalsection-constructor.md)|Инициализирует объект синхронизации, аналогичны объект mutex, но может использоваться только потоки одного процесса.|  
|[Деструктор CriticalSection::~CriticalSection](../windows/criticalsection-tilde-criticalsection-destructor.md)|Деинициализирует и уничтожает текущего **CriticalSection** объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод CriticalSection::TryLock](../windows/criticalsection-trylock-method.md)|Пытается войти в критическую секцию без блокировки. Если вызов был успешным, вызывающий поток получает права владения критический раздел.|  
|[Метод CriticalSection::Lock](../windows/criticalsection-lock-method.md)|Ожиданий владения объектом указанного критический раздел. Функция возвращает при предоставлении владельцем вызывающего потока.|  
|[Метод CriticalSection::IsValid](../windows/criticalsection-isvalid-method.md)|Указывает, является ли допустимым текущую критическую секцию.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[Элемент данных CriticalSection::cs_](../windows/criticalsection-cs-data-member.md)|Объявляет член данных критического раздела.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CriticalSection`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)