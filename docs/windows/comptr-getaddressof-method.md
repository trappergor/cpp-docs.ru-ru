---
title: Метод ComPtr::GetAddressOf | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::GetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- GetAddressOf method
ms.assetid: 972a41d0-c2ef-4ae3-b2cd-77cc45156ac9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c1be1dd844b08be23312848f007e4a57dbd893b5
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646989"
---
# <a name="comptrgetaddressof-method"></a>Метод ComPtr::GetAddressOf
Извлекает адрес [ptr_](../windows/comptr-ptr-data-member.md) элемент данных, который содержит указатель на интерфейс, представленный этим **ComPtr**.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
T* const* GetAddressOf() const;  
T** GetAddressOf();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Адрес переменной.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)