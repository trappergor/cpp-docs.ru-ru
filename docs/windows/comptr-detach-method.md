---
title: "Метод ComPtr::Detach | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::Detach
dev_langs: C++
helpviewer_keywords: Detach method
ms.assetid: b9016775-1ade-4581-be1f-0d6f9c2ca658
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: feb76819ce032608fdc717b3176f0242149eb8a3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="comptrdetach-method"></a>Метод ComPtr::Detach
Отменяет связь этого объекта `ComPtr` с интерфейсом, который он представляет.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
T* Detach();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс, который был представлен этим объектом `ComPtr`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)