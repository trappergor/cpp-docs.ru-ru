---
title: Метод HandleT::Close | Документация Майкрософт
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
ms.openlocfilehash: 7cbe76cdea5c8fadef818ede1d63d88e4437bdae
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651071"
---
# <a name="handletclose-method"></a>Метод HandleT::Close
Закрывает текущий **HandleT** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void Close();  
```  
  
## <a name="remarks"></a>Примечания  
 Дескриптор, лежащий в основе текущего **HandleT** закрывается и **HandleT** присваивается недопустимое состояние.  
  
 Если дескриптор не закрывается правильно, возникает исключение в вызывающем потоке.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)