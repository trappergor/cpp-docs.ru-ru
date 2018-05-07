---
title: Класс LOCK | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a860f79b740e0f34eef33b7a96e0236835f1f6b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="lock-class"></a>Класс lock
Этот класс позволяет автоматизировать блокировка для синхронизации доступа к объекту из нескольких потоков.  При создании получит блокировку и при уничтожении его выпуски блокировки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
ref class lock;  
```  
  
## <a name="remarks"></a>Примечания  
 `lock` доступен только для объектов среды CLR и может использоваться только в коде среды CLR.  
  
 На внутреннем уровне класс использует блокировку <xref:System.Threading.Monitor> для синхронизации доступа. См. в этом разделе для получения дополнительных сведений о процессе синхронизации.  
  
## <a name="requirements"></a>Требования  
 **Файл заголовка** \<msclr\lock.h >  
  
 **Пространство имен** msclr  
  
## <a name="see-also"></a>См. также  
 [lock](../dotnet/lock.md)   
 [Члены lock](../dotnet/lock-members.md)