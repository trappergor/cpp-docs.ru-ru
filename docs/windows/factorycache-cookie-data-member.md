---
title: "Элемент данных Factorycache::cookie | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Details::FactoryCache::cookie
dev_langs: C++
helpviewer_keywords: cookie data member
ms.assetid: b1bc79af-a896-4e3b-8afa-64733022eddf
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c3cca7b708f7fc2a0fdaa5b975396958b967210a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="factorycachecookie-data-member"></a>Элемент данных FactoryCache::cookie
Поддерживает инфраструктуру библиотека шаблонов C++ среды выполнения Windows и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
union {   
   WINRT_REGISTRATION_COOKIE winrt;  
   DWORD com;   
} cookie;  
```  
  
## <a name="remarks"></a>Примечания  
 Содержит значение, которое идентифицирует зарегистрированный объект класса среды выполнения Windows или COM, а впоследствии будет использоваться для отмены регистрации объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Factorycache-структура](../windows/factorycache-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)