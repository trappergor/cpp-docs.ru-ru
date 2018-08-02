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
ms.openlocfilehash: 1a4ec737c3f24899e50220c3e862283b88a826b9
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461168"
---
# <a name="comptroperator-microsoftwrldetailsbooltype-operator"></a>Оператор ComPtr::operator Microsoft::WRL::Details::BoolType
Указывает ли **ComPtr** управление временем существования объектов интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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