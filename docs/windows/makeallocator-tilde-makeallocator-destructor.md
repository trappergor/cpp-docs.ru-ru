---
title: "MakeAllocator:: ~ MakeAllocator деструктор | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::MakeAllocator::~MakeAllocator
dev_langs: C++
helpviewer_keywords: ~MakeAllocator, destructor
ms.assetid: f1299c5f-cc6b-4d4e-85d4-aee1be0e2b0a
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 70d89466cd71fb9884b67f9545f1fe6a7c1f5061
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="makeallocatormakeallocator-destructor"></a>Деструктор MakeAllocator::~MakeAllocator
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
~MakeAllocator();  
```  
  
## <a name="remarks"></a>Примечания  
 Деинициализирует текущий экземпляр класса MakeAllocator.  
  
 Этот деструктор также удаляет базовой выделенную память при необходимости.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [MakeAllocator-класс](../windows/makeallocator-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)