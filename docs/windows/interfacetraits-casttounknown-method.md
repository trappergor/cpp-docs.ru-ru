---
title: "Метод InterfaceTraits::CastToUnknown | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
dev_langs: C++
helpviewer_keywords: CastToUnknown method
ms.assetid: aca47fa0-3c60-47f2-a73c-258f7160adff
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e14c5e70c4854e1f3263a26a0075373248ae9d90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="interfacetraitscasttounknown-method"></a>Метод InterfaceTraits::CastToUnknown
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<  
   typename T  
>  
static __forceinline IUnknown* CastToUnknown(  
   _In_ T* ptr  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип параметра `ptr`.  
  
 `ptr`  
 Указатель на тип `T`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IUnknown, из которого `Base` является производным.  
  
## <a name="remarks"></a>Примечания  
 Приводит определенный указатель на указатель на IUnknown.  
  
 Дополнительные сведения о `Base`, см. в разделе определения открытых типов в [InterfaceTraits-структура](../windows/interfacetraits-structure.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [InterfaceTraits-структура](../windows/interfacetraits-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)