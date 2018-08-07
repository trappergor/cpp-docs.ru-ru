---
title: Элемент данных Eventsource::targets_ | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::targets_
dev_langs:
- C++
helpviewer_keywords:
- targets_ data member
ms.assetid: 5d5cee05-3315-4514-bce2-19173c923c7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e8782d66683d0a242e5321e8e3a0c8ab24b6f358
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39568853"
---
# <a name="eventsourcetargets-data-member"></a>Элемент данных EventSource::targets_
Массив из одного или нескольких обработчиков событий.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
ComPtr<Details::EventTargetArray> targets_;  
```  
  
## <a name="remarks"></a>Примечания  
 Когда события, представленного текущим **EventSource** объект встречается, обработчики событий вызываются.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс EventSource](../windows/eventsource-class.md)