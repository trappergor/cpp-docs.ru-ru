---
title: Класс DontUseNewUseMake | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
dev_langs:
- C++
helpviewer_keywords:
- DontUseNewUseMake class
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f343d0b47d50cd375d186c29ff55b91898aa9c61
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake - класс
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class DontUseNewUseMake;  
```  
  
## <a name="remarks"></a>Примечания  
 Предотвращает использование оператора `new` в RuntimeClass. Следовательно, необходимо использовать [функция](../windows/make-function.md) вместо него.  
  
## <a name="members"></a>Участники  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Оператор DontUseNewUseMake::operator new](../windows/dontusenewusemake-operator-new-operator.md)|Перегружает оператор `new` и препятствует его использованию в RuntimeClass.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `DontUseNewUseMake`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::wrl:: Details](../windows/microsoft-wrl-details-namespace.md)   
 [Функция Make](../windows/make-function.md)