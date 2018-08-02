---
title: Метод ComPtrRef::ReleaseAndGetAddressOf | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- ReleaseAndGetAddressOf method
ms.assetid: 004aac42-e135-41ce-8d1d-4c5969d55004
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 631f27dc7124cfce655f6a254548335ca8f1039f
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465413"
---
# <a name="comptrrefreleaseandgetaddressof-method"></a>Метод ComPtrRef::ReleaseAndGetAddressOf
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
InterfaceType** ReleaseAndGetAddressOf();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс, который был представлен в удаленные **ComPtrRef** объекта.  
  
## <a name="remarks"></a>Примечания  
 Удаляет текущий **ComPtrRef** и возвращает указатель на указатель на интерфейс, который был представлен **ComPtrRef** объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Comptrref-класс](../windows/comptrref-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)