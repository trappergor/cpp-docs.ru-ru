---
title: Метод InterfaceTraits::CanCastTo | Документы Microsoft
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
ms.openlocfilehash: e2a0a37f4ef9fa8f2aa92405b4b2c01d99386555
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879585"
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
  
#### <a name="parameters"></a>Параметры  
 `ptr`  
 Имя указателя на тип.  
  
 `riid`  
 Идентификатор интерфейса `Base`.  
  
 `ppv`  
 Если операция завершилась успешно, `ppv` указывает на интерфейсе, указанном свойством `Base`. В противном случае `ppv` равно `nullptr`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true` Если операция завершилась успешно и `ptr` приведен к указателю на `Base`; в противном случае `false` .  
  
## <a name="remarks"></a>Примечания  
 Указывает ли заданный указатель может быть приведен к указателю на `Base`.  
  
 Дополнительные сведения о `Base`, см. в разделе определения открытых типов в [InterfaceTraits-структура](../windows/interfacetraits-structure.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [InterfaceTraits-структура](../windows/interfacetraits-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)