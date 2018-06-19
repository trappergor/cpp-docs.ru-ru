---
title: Агрегат | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 760a595274ba7a1901138cc0cceceddf97122725
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32353967"
---
# <a name="aggregation"></a>Статистическая обработка
Бывают случаи, когда реализации объекта хотели бы воспользоваться преимуществами служб, предоставляемых другой, предварительно подготовленный объект. Кроме того желательно этот второй объект в виде естественным часть первого. COM достигает оба этих целей через вложения и статистической обработки.  
  
 Агрегат означает, что вмещающего объекта (внешнего) создает содержащегося объекта (внутренний) в процессе ее создания и интерфейсы внутреннего объекта предоставляются внешним. Объект позволяет сам допускающим статистическую обработку или нет. Если Да, оно должно соответствовать определенным правилам для статистической обработки для правильной работы.  
  
 В первую очередь, все **IUnknown** вызовы методов для содержащегося объекта должны делегировать вмещающего объекта.  
  
## <a name="see-also"></a>См. также  
 [Знакомство с COM](../atl/introduction-to-com.md)   
 [Повторное использование объектов](http://msdn.microsoft.com/library/windows/desktop/ms678443)

