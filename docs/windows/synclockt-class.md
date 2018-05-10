---
title: Класс SyncLockT | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT class
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e05a1be5d84db52573d3c3235936ecf82dde5894
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="synclockt-class"></a>SyncLockT - класс
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockT;  
```  
  
#### <a name="parameters"></a>Параметры  
 `SyncTraits`  
 Тип, который может стать владельцем ресурса.  
  
## <a name="remarks"></a>Примечания  
 Представляет тип, который может принимать монопольного или общие права владения ресурсом.  
  
 Класс SyncLockT используется, например, чтобы реализовать [SRWLock](../windows/srwlock-class.md) класса.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор SyncLockT::SyncLockT](../windows/synclockt-synclockt-constructor.md)|Инициализирует новый экземпляр класса SyncLockT.|  
|[Деструктор SyncLockT::~SyncLockT](../windows/synclockt-tilde-synclockt-destructor.md)|Отменяет инициализацию экземпляра класса SyncLockT.|  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор SyncLockT::SyncLockT](../windows/synclockt-synclockt-constructor.md)|Инициализирует новый экземпляр класса SyncLockT.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод SyncLockT::IsLocked](../windows/synclockt-islocked-method.md)|Указывает, владеет ли текущий объект SyncLockT ресурсом; Объект SyncLockT является *заблокирован*.|  
|[Метод SyncLockT::Unlock](../windows/synclockt-unlock-method.md)|Передает управление ресурса, удерживаемого текущий объект SyncLockT, если таковые имеются.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание|  
|----------|-----------------|  
|[Элемент данных SyncLockT::sync_](../windows/synclockt-sync-data-member.md)|Удерживает базовый ресурс, представленный классом SyncLockT.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `SyncLockT`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers::Details](../windows/microsoft-wrl-wrappers-details-namespace.md)   
 [Класс SRWLock](../windows/srwlock-class.md)