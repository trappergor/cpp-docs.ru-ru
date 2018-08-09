---
title: Boolstruct-структура | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::BoolStruct
dev_langs:
- C++
helpviewer_keywords:
- BoolStruct structure
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 14e3d81ca273bf96b4812f08a46904c9d521c5cf
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650486"
---
# <a name="boolstruct-structure"></a>BoolStruct - структура
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
struct BoolStruct;  
```  
  
## <a name="remarks"></a>Примечания  
 **BoolStruct** структура определяет ли `ComPtr` управление временем существования объектов интерфейса. **BoolStruct** внутренне используется элементом [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) оператор.  
  
## <a name="members"></a>Участники  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Элемент данных BoolStruct::Member](../windows/boolstruct-member-data-member.md)|Указывает, что [ComPtr](../windows/comptr-class.md) является, или не, управление временем существования объектов интерфейса.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `BoolStruct`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** internal.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::wrl:: Details](../windows/microsoft-wrl-details-namespace.md)   
 [Оператор ComPtr::operator Microsoft::WRL::Details::BoolType](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)