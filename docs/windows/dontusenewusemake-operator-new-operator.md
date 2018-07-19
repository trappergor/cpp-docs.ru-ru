---
title: Оператор Dontusenewusemake::operator new | Документы Microsoft
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
ms.openlocfilehash: 9785ea27c79ff0a118ff3697a22804c520b265ee
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873684"
---
# <a name="dontusenewusemakeoperator-new-operator"></a>Оператор DontUseNewUseMake::operator new
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void* operator new(  
   size_t,  
   _In_ void* placement  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `__unnamed0`  
 Неименованный параметр, который определяет количество байт памяти для выделения.  
  
 `placement`  
 Выделяемый тип.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Предоставляет способ передачи дополнительных аргументов при перегрузке оператора `new`.  
  
## <a name="remarks"></a>Примечания  
 Перегружает оператор `new` и препятствует его использованию в RuntimeClass.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Dontusenewusemake-класс](../windows/dontusenewusemake-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)