---
title: "Перечисление RuntimeClassType | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClassType
dev_langs: C++
helpviewer_keywords: RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 26016e8c95807af76484504c491ca1e6e08f8f96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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