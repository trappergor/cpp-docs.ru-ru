---
title: "Метод ComPtrRef::ReleaseAndGetAddressOf | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf
dev_langs: C++
helpviewer_keywords: ReleaseAndGetAddressOf method
ms.assetid: 004aac42-e135-41ce-8d1d-4c5969d55004
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 216e1b5e2a9343e780858c0f19578d970cead593
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="comptrrefreleaseandgetaddressof-method"></a>Метод ComPtrRef::ReleaseAndGetAddressOf
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
InterfaceType** ReleaseAndGetAddressOf();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс, представленный удаленным объектом ComPtrRef.  
  
## <a name="remarks"></a>Примечания  
 Удаляет текущий объект ComPtrRef и возвращает указатель на указатель на интерфейс, представленный объектом ComPtrRef.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [ComPtrRef-класс](../windows/comptrref-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)