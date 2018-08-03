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
ms.openlocfilehash: 4d4a84131a6159c665e3947d7b642ab0592b2e36
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465442"
---
# <a name="comptrdetach-method"></a>Метод ComPtr::Detach
Отменяет связь этого **ComPtr** объекта с интерфейсом, который он представляет.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
T* Detach();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс, который был представлен этим **ComPtr** объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)