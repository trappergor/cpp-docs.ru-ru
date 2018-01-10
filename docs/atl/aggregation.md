---
title: "Агрегат | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8dbb0332bc7e55464e5b8af9d0b57e236f23dc86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="aggregation"></a>Статистическая обработка
Бывают случаи, когда реализации объекта хотели бы воспользоваться преимуществами служб, предоставляемых другой, предварительно подготовленный объект. Кроме того желательно этот второй объект в виде естественным часть первого. COM достигает оба этих целей через вложения и статистической обработки.  
  
 Агрегат означает, что вмещающего объекта (внешнего) создает содержащегося объекта (внутренний) в процессе ее создания и интерфейсы внутреннего объекта предоставляются внешним. Объект позволяет сам допускающим статистическую обработку или нет. Если Да, оно должно соответствовать определенным правилам для статистической обработки для правильной работы.  
  
 В первую очередь, все **IUnknown** вызовы методов для содержащегося объекта должны делегировать вмещающего объекта.  
  
## <a name="see-also"></a>См. также  
 [Знакомство с COM](../atl/introduction-to-com.md)   
 [Повторное использование объектов](http://msdn.microsoft.com/library/windows/desktop/ms678443)

