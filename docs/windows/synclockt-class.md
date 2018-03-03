---
title: "Класс SyncLockT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT class
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3f3a9794f7b00a2029f6706db3a846ba127a4d5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор SyncLockT::SyncLockT](../windows/synclockt-synclockt-constructor.md)|Инициализирует новый экземпляр класса SyncLockT.|  
|[Деструктор SyncLockT::~SyncLockT](../windows/synclockt-tilde-synclockt-destructor.md)|Отменяет инициализацию экземпляра класса SyncLockT.|  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор SyncLockT::SyncLockT](../windows/synclockt-synclockt-constructor.md)|Инициализирует новый экземпляр класса SyncLockT.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод SyncLockT::IsLocked](../windows/synclockt-islocked-method.md)|Указывает, владеет ли текущий объект SyncLockT ресурсом; Объект SyncLockT является *заблокирован*.|  
|[Метод SyncLockT::Unlock](../windows/synclockt-unlock-method.md)|Передает управление ресурса, удерживаемого текущий объект SyncLockT, если таковые имеются.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
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