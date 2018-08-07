---
title: Метод InterfaceTraits::CanCastTo | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: 275847cb-69ea-42bf-910f-05ba6ef8b48d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: df603fe8d4c063c014118caf89a74a40e73cbe5b
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607833"
---
# <a name="interfacetraitscancastto-method"></a>Метод InterfaceTraits::CanCastTo
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename T>  
static __forceinline bool CanCastTo(  
   _In_ T* ptr,  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *ptr*  
 Имя указателя на тип.  
  
 *riid*  
 Идентификатор интерфейса `Base`.  
  
 *ppv*  
 Если операция выполнена успешно, *ppv* указывает на интерфейсе, указанном свойством `Base`. В противном случае *ppv* присваивается **nullptr**.  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** при успешном выполнении этой операции и *ptr* приведен к указателю на `Base`; в противном случае **false** .  
  
## <a name="remarks"></a>Примечания  
 Указывает ли заданный указатель может быть приведен к указателю на `Base`.  
  
 Дополнительные сведения о `Base`, см. в разделе **общедоступные определения типов** статьи [interfacetraits-структура](../windows/interfacetraits-structure.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Interfacetraits-структура](../windows/interfacetraits-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)