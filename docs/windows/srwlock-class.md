---
title: Класс SRWLock | Документы Microsoft
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
ms.openlocfilehash: ec31b1469f437ff2776ed9da52fbcd7557fca8e2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="srwlock-class"></a>SRWLock - класс
Представляет тонкую блокировку чтения и записи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class SRWLock;  
```  
  
## <a name="remarks"></a>Примечания  
 Блокировки потоков чтения/записи используется для синхронизации доступа между потоками на объект или ресурсов. Дополнительные сведения см. в разделе [функций синхронизации](http://msdn.microsoft.com/en-us/9b6359c2-0113-49b6-83d0-316ad95aba1b).  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|||  
|-|-|  
|**SyncLockExclusive**|Синоним для объекта SRWLock, получаемая в монопольном режиме.|  
|**SyncLockShared**|Синоним для объекта SRWLock, получаемая в режиме общего доступа.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор SRWLock::SRWLock](../windows/srwlock-srwlock-constructor.md)|Инициализирует новый экземпляр класса SRWLock.|  
|[Деструктор SRWLock::~SRWLock](../windows/srwlock-tilde-srwlock-destructor.md)|Отменяет инициализацию экземпляра класса SRWLock.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод SRWLock::LockExclusive](../windows/srwlock-lockexclusive-method.md)|Получает объект SRWLock в монопольном режиме.|  
|[Метод SRWLock::LockShared](../windows/srwlock-lockshared-method.md)|Получает объект SRWLock в режиме общего доступа.|  
|[Метод SRWLock::TryLockExclusive](../windows/srwlock-trylockexclusive-method.md)|Пытается получить объект SRWLock в монопольном режиме для текущей или заданной объекта SRWLock.|  
|[Метод SRWLock::TryLockShared](../windows/srwlock-trylockshared-method.md)|Пытается получить объект SRWLock в режиме общего доступа для текущей или заданной объекта SRWLock.|  
  
### <a name="protected-data-member"></a>Защищенные данные-член  
  
|name|Описание|  
|----------|-----------------|  
|[Элемент данных SRWLock::SRWLock_](../windows/srwlock-srwlock-data-member.md)|Содержит базовую переменную блокировки для текущего объекта SRWLock.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `SRWLock`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)