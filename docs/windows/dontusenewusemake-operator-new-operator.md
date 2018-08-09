---
title: Оператор Dontusenewusemake::operator new | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
dev_langs:
- C++
helpviewer_keywords:
- operator new operator
ms.assetid: 6af07a0d-2271-430c-9d9b-5a4223fed049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b849c7578b29a3d4595a9ecd07c4339dc751e9dd
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652953"
---
# <a name="dontusenewusemakeoperator-new-operator"></a>Оператор DontUseNewUseMake::operator new
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void* operator new(  
   size_t,  
   _In_ void* placement  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *__unnamed0*  
 Неименованный параметр, который определяет количество байт памяти для выделения.  
  
 *Размещение*  
 Выделяемый тип.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Предоставляет способ передачи дополнительных аргументов при перегрузке оператора **новый**.  
  
## <a name="remarks"></a>Примечания  
 Перегружает оператор **новый** и предотвращает использование в `RuntimeClass`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Dontusenewusemake-класс](../windows/dontusenewusemake-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)