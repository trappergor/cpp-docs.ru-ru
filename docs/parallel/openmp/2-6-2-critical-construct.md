---
title: "2.6.2 конструкция critical | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: c46ecd00-b4a2-4a5e-ba92-288c329e773a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c658b32536404dde1a693582e78bfbedc2823b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="262-critical-construct"></a>2.6.2 Конструкция critical
**Критические** директива идентифицирует конструкцию, которая ограничивает выполнение блоку структурированных к одному потоку за раз. Синтаксис **критические** директивы таков:  
  
```  
#pragma omp critical [(name)]  new-linestructured-block  
```  
  
 Необязательный *имя* может использоваться для идентификации критической области. Идентификаторы, используемые для идентификации критической области имеют внешнюю компоновку и находятся в пространстве имен, которое отличается от пространства имен, используемые метки, теги, членов и обычные идентификаторы.  
  
 Поток ожидает в начале критической области, пока другой поток выполняется критической области (в любом месте программы) с тем же именем. Все неименованные **критические** директивы сопоставляются с тем же именем определен.