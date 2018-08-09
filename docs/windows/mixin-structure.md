---
title: Структура MixIn | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
dev_langs:
- C++
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8fb5fa5288829ef51bf818ad8b7cf3b46edb59bf
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014290"
---
# <a name="mixin-structure"></a>MixIn - структура
Гарантирует, что класс среды выполнения является производным от интерфейсов среды выполнения Windows, если таковые имеются, а затем от интерфейсов классической модели COM.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template<  
   typename Derived,  
   typename MixInType,  
   bool hasImplements = __is_base_of(Details::ImplementsBase,  
   MixInType)  
>  
struct MixIn;  
```  
  
### <a name="parameters"></a>Параметры  
 *Производные*  
 Тип, производный от [реализует](../windows/implements-structure.md) структуры.  
  
 *MixInType*  
 Базовый тип.  
  
 *hasImplements*  
 **значение true,** Если *MixInType* является производным от текущей реализации базового типа; **false** в противном случае.  
  
## <a name="remarks"></a>Примечания  
 Если класс является производным от среды выполнения Windows и интерфейсов класса модели COM, список объявления класса сначала должен перечислить все интерфейсы среды выполнения Windows, и затем любой классического COM интерфейсы. **MixIn** гарантирует, что интерфейсы будут указаны в правильном порядке.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `MixIn`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)