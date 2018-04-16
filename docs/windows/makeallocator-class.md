---
title: Класс MakeAllocator | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
dev_langs:
- C++
helpviewer_keywords:
- MakeAllocator class
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 33ba172099fd2554709cc539eeee8999c0e42cef
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="makeallocator-class"></a>MakeAllocator - класс
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
template<  
   typename T,  
   bool hasWeakReferenceSupport =   
         !__is_base_of(RuntimeClassFlags<InhibitWeakReference>, T)>
 class MakeAllocator;  
  
template<typename T>  
class MakeAllocator<T, false>;  
  
template<typename T>  
class MakeAllocator<T, true>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Имя типа.  
  
 `hasWeakReferenceSupport`  
 `true` выделить память для объекта, который поддерживает слабые ссылки; `false` выделить память для объекта, который не поддерживает слабые ссылки.  
  
## <a name="remarks"></a>Примечания  
 Выделяет память для активируемого класса, независимо от поддержки слабой ссылки.  
  
 Переопределите MakeAllocator-класс для реализации модели выделения памяти, определяемые пользователем.  
  
 MakeAllocator обычно используется для предотвращения утечек памяти в том случае, если объект создается во время построения.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор MakeAllocator::MakeAllocator](../windows/makeallocator-makeallocator-constructor.md)|Инициализирует новый экземпляр класса MakeAllocator.|  
|[Деструктор MakeAllocator::~MakeAllocator](../windows/makeallocator-tilde-makeallocator-destructor.md)|Деинициализирует текущий экземпляр класса MakeAllocator.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод MakeAllocator::Allocate](../windows/makeallocator-allocate-method.md)|Выделяет память и связывает ее с текущим объектом MakeAllocator.|  
|[Метод MakeAllocator::Detach](../windows/makeallocator-detach-method.md)|Отсоединяет памяти, выделенной с помощью [Allocate](../windows/makeallocator-allocate-method.md) метод с текущим объектом MakeAllocator.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `MakeAllocator`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)