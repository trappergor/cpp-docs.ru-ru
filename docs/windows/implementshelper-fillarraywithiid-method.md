---
title: Метод ImplementsHelper::FillArrayWithIid | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid
dev_langs:
- C++
helpviewer_keywords:
- FillArrayWithIid method
ms.assetid: f60035ee-b7d6-4a08-966d-f88c646944c3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: da38eddae5ab9c49da98a4c5e9f383d59d110ee1
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608326"
---
# <a name="implementshelperfillarraywithiid-method"></a>Метод ImplementsHelper::FillArrayWithIid
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void FillArrayWithIid(  
   _Inout_ unsigned long *index,   
   _Inout_ IID* iids) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *Индекс*  
 Отсчитываемый от нуля индекс, указывающий начальный элемент массива для этой операции. По завершении этой операции *индекс* увеличивается на 1.  
  
 *идентификаторы IID*  
 Массив типа IID.  
  
## <a name="remarks"></a>Примечания  
 Вставляет идентификатор интерфейса, заданный текущим параметром шаблона признаками в указанный элемент массива.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Implementshelper-структура](../windows/implementshelper-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)