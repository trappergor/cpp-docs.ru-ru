---
title: Мьютекс Class1 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex
dev_langs:
- C++
helpviewer_keywords:
- Mutex class
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9a9e9674dd8ac5aa7d444a77df66c1aff4a70299
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878415"
---
# <a name="mutex-class1"></a>Мьютекс Class1
Представляет объект синхронизации, который исключительно управляет общим ресурсом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class Mutex : public HandleT<HandleTraits::MutexTraits>  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|**SyncLock**|Синоним для класса, который поддерживает синхронные блокировки.|  
  
### <a name="public-constructor"></a>Открытый конструктор  
  
|name|Описание|  
|----------|-----------------|  
|[Конструктор Mutex::Mutex](../windows/mutex-mutex-constructor.md)|Инициализирует новый экземпляр класса Mutex.|  
  
### <a name="public-members"></a>Открытые члены  
  
|name|Описание|  
|----------|-----------------|  
|[Метод Mutex::Lock](../windows/mutex-lock-method.md)|Ожидает, пока текущий объект или объект мьютекса, связанный с указанным дескриптором освобождает объект взаимного исключения или истечения отведенного времени ожидания.|  
  
### <a name="public-operator"></a>Открытый оператор  
  
|name|Описание|  
|----------|-----------------|  
|[Оператор Mutex::operator=](../windows/mutex-operator-assign-operator.md)|Назначает (перемещается) указанный мьютекс объекта на текущий объект Mutex.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `Mutex`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)