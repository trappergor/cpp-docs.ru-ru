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
ms.openlocfilehash: 94c246153e5c7e159ccbfe4196ab3692f4138047
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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