---
title: "Класс Semaphore | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
dev_langs:
- C++
helpviewer_keywords:
- Semaphore class
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 60373c12220fce57672389b98455a123990f3c93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="semaphore-class"></a>Semaphore - класс
Представляет объект синхронизации, который управляет общим ресурсом и поддерживает ограниченное число пользователей.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|`SyncLock`|Синоним для класса, который поддерживает синхронные блокировки.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор Semaphore::Semaphore](../windows/semaphore-semaphore-constructor.md)|Инициализирует новый экземпляр класса Semaphore.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод InvokeHelper::Invoke](../windows/invokehelper-invoke-method.md)|Вызывает обработчик событий, сигнатура которого содержит указанное число аргументов.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод Semaphore::Lock](../windows/semaphore-lock-method.md)|Ожидает, пока текущий объект или объект, связанный с указанным дескриптором находится в состоянии получения сигнала или истечении отведенного времени ожидания.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Оператор Semaphore::operator=](../windows/semaphore-operator-assign-operator.md)|Перемещает заданный дескриптор из объекта семафора для текущего объекта семафора.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `Semaphore`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)