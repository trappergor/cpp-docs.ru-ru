---
title: Метод ComPtr::Detach | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: b9016775-1ade-4581-be1f-0d6f9c2ca658
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: abc30204969464323d4995310cee0866139734fc
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648013"
---
# <a name="comptrdetach-method"></a>Метод ComPtr::Detach
Отменяет связь этого **ComPtr** объекта с интерфейсом, который он представляет.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
T* Detach();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс, который был представлен этим **ComPtr** объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)