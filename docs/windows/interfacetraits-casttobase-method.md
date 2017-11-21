---
title: "Метод InterfaceTraits::CastToBase | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::InterfaceTraits::CastToBase
dev_langs: C++
helpviewer_keywords: CastToBase method
ms.assetid: 0591a017-0adf-4358-b946-eb0a307ce7f2
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fa78bd28bbc65c93c201f044055cde40d5d79cf6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="interfacetraitscasttobase-method"></a>Метод InterfaceTraits::CastToBase
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<  
   typename T  
>  
static __forceinline Base* CastToBase(  
   _In_ T* ptr  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип параметра `ptr`.  
  
 `ptr`  
 Указатель на тип `T`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на `Base`.  
  
## <a name="remarks"></a>Примечания  
 Приводит определенный указатель к указателю на `Base`.  
  
 Дополнительные сведения о `Base`, см. в разделе определения открытых типов в [InterfaceTraits-структура](../windows/interfacetraits-structure.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [InterfaceTraits-структура](../windows/interfacetraits-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)