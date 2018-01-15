---
title: "Метод HandleT::Close | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
dev_langs: C++
helpviewer_keywords: Close method
ms.assetid: 1b9d597c-abcf-4028-a068-0344560009f6
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c2edd3fee9893c72685eb334bf4b361997646b7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="handletclose-method"></a>Метод HandleT::Close
Закрытие текущего объекта HandleT.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void Close();  
```  
  
## <a name="remarks"></a>Примечания  
 Дескриптор, лежащий в основе текущего объекта HandleT, закрывается и объекту HandleT присваивается недопустимое состояние.  
  
 Если дескриптор не закрывается правильно, возникает исключение в вызывающем потоке.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)