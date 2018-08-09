---
title: SRWLOCK-класс | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock
dev_langs:
- C++
helpviewer_keywords:
- SRWLock class
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 58b537a29a042f2227f3c2c121a320532d52877c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016370"
---
# <a name="srwlock-class"></a>SRWLock - класс
Представляет тонкую блокировку чтения и записи.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
class SRWLock;  
```  
  
## <a name="remarks"></a>Примечания  
 Блокировки потоков чтения/записи используется для синхронизации доступа между потоками для объекта или ресурса. Дополнительные сведения см. в разделе [функций синхронизации](http://msdn.microsoft.com/9b6359c2-0113-49b6-83d0-316ad95aba1b).  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|||  
|-|-|  
|`SyncLockExclusive`|Синоним для **SRWLock** объекта, получившего в монопольном режиме.|  
|`SyncLockShared`|Синоним для **SRWLock** объекта, получившего в режиме общего доступа.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор SRWLock::SRWLock](../windows/srwlock-srwlock-constructor.md)|Инициализирует новый экземпляр класса **SRWLock** класса.|  
|[Деструктор SRWLock::~SRWLock](../windows/srwlock-tilde-srwlock-destructor.md)|Отменяет инициализацию экземпляра **SRWLock** класса.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод SRWLock::LockExclusive](../windows/srwlock-lockexclusive-method.md)|Получает **SRWLock** объекта в монопольном режиме.|  
|[Метод SRWLock::LockShared](../windows/srwlock-lockshared-method.md)|Получает **SRWLock** объект в режиме общего доступа.|  
|[Метод SRWLock::TryLockExclusive](../windows/srwlock-trylockexclusive-method.md)|Пытается получить **SRWLock** объекта в монопольном режиме для текущей или заданной **SRWLock** объекта.|  
|[Метод SRWLock::TryLockShared](../windows/srwlock-trylockshared-method.md)|Пытается получить **SRWLock** объект в режиме общего доступа для текущей или заданной **SRWLock** объекта.|  
  
### <a name="protected-data-member"></a>Защищенные данные-член  
  
|name|Описание:|  
|----------|-----------------|  
|[Элемент данных SRWLock::SRWLock_](../windows/srwlock-srwlock-data-member.md)|Содержит базовой переменной блокировки для текущего **SRWLock** объекта.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `SRWLock`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)