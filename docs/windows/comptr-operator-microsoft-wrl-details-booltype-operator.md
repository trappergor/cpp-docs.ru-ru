---
title: "ComPtr::operator:: Booltype | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 010979a0a72fc1d522a921b20df4579bc6efa159
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="comptroperator-microsoftwrldetailsbooltype-operator"></a>Оператор ComPtr::operator Microsoft::WRL::Details::BoolType
Указывает, управляет ли ComPtr временем существования объекта интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если интерфейс связан с этим объектом ComPtr, адрес [BoolStruct::Member](../windows/boolstruct-member-data-member.md) данные-член; в противном случае `nullptr`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)   
 [Метод ComPtr::Get](../windows/comptr-get-method.md)