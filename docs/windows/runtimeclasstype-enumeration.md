---
title: Перечисление RuntimeClassType | Документация Майкрософт
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
ms.openlocfilehash: 4464d236a85e06bf907f738657a4a0707e14a5e1
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603505"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType - перечисление
Указывает тип [RuntimeClass](../windows/runtimeclass-class.md) экземпляр, который поддерживается.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
enum RuntimeClassType;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="values"></a>Значения  
  
|Имя|Описание:|  
|----------|-----------------|  
|`ClassicCom`|Классического COM-класс среды выполнения.|  
|`Delegate`|Аналогично параметру `ClassicCom`.|  
|`InhibitFtmBase`|Отключает `FtmBase` поддержку во время работы `__WRL_CONFIGURATION_LEGACY__` не определен.|  
|`InhibitWeakReference`|Отключает поддержку слабых ссылок.|  
|`WinRt`|Класс среды выполнения Windows.|  
|`WinRtClassicComMix`|Комбинация `WinRt` и `ClassicCom`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)