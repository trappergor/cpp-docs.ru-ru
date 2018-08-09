---
title: Dontusenewusemake-класс | Документация Майкрософт
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
ms.openlocfilehash: 32418b163cb31f5eaf20c9d2b3ff3a4b585850dd
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644103"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake - класс
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
class DontUseNewUseMake;  
```  
  
## <a name="remarks"></a>Примечания  
 Предотвращает использование оператора **новый** в `RuntimeClass`. Следовательно, необходимо использовать [функция](../windows/make-function.md) вместо этого.  
  
## <a name="members"></a>Участники  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Оператор DontUseNewUseMake::operator new](../windows/dontusenewusemake-operator-new-operator.md)|Перегружает оператор **новый** и предотвращает использование в `RuntimeClass`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `DontUseNewUseMake`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::wrl:: Details](../windows/microsoft-wrl-details-namespace.md)   
 [Функция Make](../windows/make-function.md)