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
ms.openlocfilehash: 69f3f2c756d158954676f6fc42941b1b80f4345e
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569922"
---
# <a name="handletclose-method"></a>Метод HandleT::Close
Закрывает текущий **HandleT** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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