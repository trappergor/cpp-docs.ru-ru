---
title: Метод InterfaceTraits::CastToUnknown | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: aca47fa0-3c60-47f2-a73c-258f7160adff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bdb87fe43b5cc6a5d2c141ac534e3b5e781f91e8
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019921"
---
# <a name="interfacetraitscasttounknown-method"></a>Метод InterfaceTraits::CastToUnknown
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename T>  
static __forceinline IUnknown* CastToUnknown(  
   _In_ T* ptr  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Тип параметра *ptr*.  
  
 *ptr*  
 Указатель на тип *T*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IUnknown, из которого `Base` является производным.  
  
## <a name="remarks"></a>Примечания  
 Приводит определенный указатель к указателю на `IUnknown`.  
  
 Дополнительные сведения о `Base`, см. в разделе общедоступные определения типов в [interfacetraits-структура](../windows/interfacetraits-structure.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Interfacetraits-структура](../windows/interfacetraits-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)