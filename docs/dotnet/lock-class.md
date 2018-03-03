---
title: "Класс LOCK | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
dev_langs:
- C++
helpviewer_keywords:
- lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c2f2a8e371803d33a2c42508ec595681ada3bab8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="lock-class"></a>Класс lock
Этот класс позволяет автоматизировать блокировка для синхронизации доступа к объекту из нескольких потоков.  При создании получит блокировку и при уничтожении его выпуски блокировки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
ref class lock;  
```  
  
## <a name="remarks"></a>Примечания  
 `lock`доступен только для объектов среды CLR и может использоваться только в коде среды CLR.  
  
 На внутреннем уровне класс использует блокировку <xref:System.Threading.Monitor> для синхронизации доступа. См. в этом разделе для получения дополнительных сведений о процессе синхронизации.  
  
## <a name="requirements"></a>Требования  
 **Файл заголовка** \<msclr\lock.h >  
  
 **Пространство имен** msclr  
  
## <a name="see-also"></a>См. также  
 [Блокировка](../dotnet/lock.md)   
 [Члены lock](../dotnet/lock-members.md)