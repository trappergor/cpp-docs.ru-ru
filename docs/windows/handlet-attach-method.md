---
title: Метод HandleT::Attach | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method
ms.assetid: a8783a18-bbf6-456c-98a3-e2048a10d79f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5db96e9b8fd2090d9c58d9458bd53c66f6162477
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569176"
---
# <a name="handletattach-method"></a>Метод HandleT::Attach
Связывает указанный дескриптор с текущим **HandleT** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void Attach(  
   typename HandleTraits::Type h  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *h*  
 Дескриптор.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)