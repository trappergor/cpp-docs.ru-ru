---
title: Структура ImplementsHelper | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper
dev_langs:
- C++
helpviewer_keywords:
- ImplementsHelper structure
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 58f27e418946987633f771bc8d2c3224bc2cd7fd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33875943"
---
# <a name="implementshelper-structure"></a>ImplementsHelper - структура
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   typename RuntimeClassFlagsT,  
   typename ILst,  
   bool IsDelegateToClass  
>  
friend struct Details::ImplementsHelper;  
```  
  
#### <a name="parameters"></a>Параметры  
 `RuntimeClassFlagsT`  
 Поле флагов, которое указывает один или несколько [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) перечислителей.  
  
 `ILst`  
 Список идентификаторов интерфейса.  
  
 `IsDelegateToClass`  
 Укажите `true` , если текущий экземпляр реализует является базовым классом первого идентификатора интерфейса в `ILst`; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 Помогает реализовать [реализует](../windows/implements-structure.md) структуры.  
  
 Этот шаблон просматривает список интерфейсов и добавляет их в качестве базовых классов, а также как сведения, необходимые для включения QueryInterface.  
  
## <a name="members"></a>Участники  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ImplementsHelper`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Справочник (библиотека среды выполнения Windows)](http://msdn.microsoft.com/en-us/00000000-0000-0000-0000-000000000000)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)