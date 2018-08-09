---
title: Метод ComPtr::ReleaseAndGetAddressOf | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- ReleaseAndGetAddressOf method
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3bded6992abc5b22e2c02a3364431a3f68b76ad6
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649852"
---
# <a name="comptrreleaseandgetaddressof-method"></a>Метод ComPtr::ReleaseAndGetAddressOf
Освобождает интерфейс, связанный с данным **ComPtr** , а затем извлекает адрес [ptr_](../windows/comptr-ptr-data-member.md) элемент данных, который содержит указатель на интерфейс, который был выпущен.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
T** ReleaseAndGetAddressOf();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Адрес [ptr_](../windows/comptr-ptr-data-member.md) данными-членом это **ComPtr**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)   
 [Элемент данных ComPtr::ptr_](../windows/comptr-ptr-data-member.md)