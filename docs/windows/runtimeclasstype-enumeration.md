---
title: Перечисление RuntimeClassType | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 43ab0a738af4c6bc92d42c0884827b574946d2ea
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType - перечисление
Указывает тип [RuntimeClass](../windows/runtimeclass-class.md) экземпляр, который поддерживается.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
enum RuntimeClassType;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`ClassicCom`|Классический COM класса среды выполнения.|  
|`Delegate`|Эквивалентно **ClassicCom**.|  
|`InhibitFtmBase`|Отключает `FtmBase` поддержки при `__WRL_CONFIGURATION_LEGACY__` не определен.|  
|`InhibitWeakReference`|Отключает поддержку слабых ссылок.|  
|`WinRt`|Класс среды выполнения Windows.|  
|`WinRtClassicComMix`|Комбинация `WinRt` и `ClassicCom`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)