---
title: Метод HandleT::Close | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 1b9d597c-abcf-4028-a068-0344560009f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4f0c1e47420106651cfe0526d6d212e9819a72ff
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
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