---
title: 'Оператор ComPtr::operator:: Booltype | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb5735eeb9cd4048596588765468fbb9c5e07496
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652605"
---
# <a name="comptroperator-microsoftwrldetailsbooltype-operator"></a>Оператор ComPtr::operator Microsoft::WRL::Details::BoolType
Указывает ли **ComPtr** управление временем существования объектов интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если интерфейс связан с данным **ComPtr**, адрес [BoolStruct::Member](../windows/boolstruct-member-data-member.md) данные-член; в противном случае **nullptr**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)   
 [Метод ComPtr::Get](../windows/comptr-get-method.md)