---
title: "Можно разместить несколько элементов управления в одном окне | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [ATL], hosting multiple
- windows [C++], hosting multiple controls
ms.assetid: 3a967a1a-7e7e-42e3-8eed-f7bde912363f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: be87c0bad9ab250593847cc24d16158030040054
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="can-i-host-more-than-one-control-in-a-single-window"></a>Можно разместить несколько элементов управления в одном окне
Более одного элемента управления в одном окне узла ATL невозможна. Каждое окно узла предназначен для хранения ровно один элемент управления одновременно (Это обеспечивает простой механизм для обработки сообщения отражения и на уровне элемента управления свойства окружения). Однако если необходимо видеть несколько элементов управления в одном окне, это простой механизм для создания нескольких окон узла как дочерние элементы этого окна.  
  
## <a name="see-also"></a>См. также  
 [Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)

