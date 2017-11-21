---
title: "Метод HandleT::Attach | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleT::Attach
dev_langs: C++
helpviewer_keywords: Attach method
ms.assetid: a8783a18-bbf6-456c-98a3-e2048a10d79f
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 572221b7232e25984d78ec903f8d13b9e08ba06b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="handletattach-method"></a>Метод HandleT::Attach
Связывает указанный дескриптор с текущего объекта HandleT.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void Attach(  
   typename HandleTraits::Type h  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `h`  
 Дескриптор.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)