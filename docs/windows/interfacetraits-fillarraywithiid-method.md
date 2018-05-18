---
title: Метод InterfaceTraits::FillArrayWithIid | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid
dev_langs:
- C++
helpviewer_keywords:
- FillArrayWithIid method
ms.assetid: 73583177-adc9-4fcb-917d-fa7e6d07c990
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e6e32b2e40ba9dc2b8085f8edc99beb899e90ace
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="interfacetraitsfillarraywithiid-method"></a>Метод InterfaceTraits::FillArrayWithIid
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__forceinline static void FillArrayWithIid(  
   _Inout_ unsigned long &index,  
   _In_ IID* iids  
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `index`  
 Указатель на поле, содержащее значение отсчитываемый от нуля индекс.  
  
 `iids`  
 Массив идентификаторов интерфейса.  
  
## <a name="remarks"></a>Примечания  
 Назначает идентификатор интерфейса `Base` на элемент массива, заданного аргументом индекса.  
  
 В отличие от имени этого API только один массив элемент изменен; не весь массив.  
  
 Дополнительные сведения о `Base`, см. в разделе определения открытых типов в [InterfaceTraits-структура](../windows/interfacetraits-structure.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [InterfaceTraits-структура](../windows/interfacetraits-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)