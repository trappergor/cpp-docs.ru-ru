---
title: Метод ComPtr::ReleaseAndGetAddressOf | Документы Microsoft
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
ms.openlocfilehash: 32d846a1fc41596812ca6e8578f25f9ae8115182
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="comptrreleaseandgetaddressof-method"></a>Метод ComPtr::ReleaseAndGetAddressOf
Освобождает интерфейс, связанный с данным объектом ComPtr, а затем извлекает адрес данных-члена [ptr_](../windows/comptr-ptr-data-member.md) , который содержит указатель на освобожденный интерфейс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
T** ReleaseAndGetAddressOf();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Адрес [ptr_](../windows/comptr-ptr-data-member.md) элемента данных этого объекта ComPtr.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)   
 [Элемент данных ComPtr::ptr_](../windows/comptr-ptr-data-member.md)