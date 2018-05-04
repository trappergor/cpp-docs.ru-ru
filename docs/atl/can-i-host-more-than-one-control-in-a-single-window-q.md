---
title: Можно разместить несколько элементов управления в одном окне | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL], hosting multiple
- windows [C++], hosting multiple controls
ms.assetid: 3a967a1a-7e7e-42e3-8eed-f7bde912363f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ceb9444b6371e261115bbf52ef5a249100772d1f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="can-i-host-more-than-one-control-in-a-single-window"></a>Можно разместить несколько элементов управления в одном окне
Более одного элемента управления в одном окне узла ATL невозможна. Каждое окно узла предназначен для хранения ровно один элемент управления одновременно (Это обеспечивает простой механизм для обработки сообщения отражения и на уровне элемента управления свойства окружения). Однако если необходимо видеть несколько элементов управления в одном окне, это простой механизм для создания нескольких окон узла как дочерние элементы этого окна.  
  
## <a name="see-also"></a>См. также  
 [Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)

