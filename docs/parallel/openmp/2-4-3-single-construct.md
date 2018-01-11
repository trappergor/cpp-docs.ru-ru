---
title: "2.4.3 одна конструкция | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 72dc551986f149bda668c438ac5f51d01d530c51
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="243-single-construct"></a>2.4.3 Конструкция single
**Одного** директива идентифицирует конструкцию, которая указывает, что связанный структурированный блок выполняется только одним потоком в группе (не обязательно главного потока). Синтаксис **одного** директивы таков:  
  
```  
#pragma omp single [clause[[,] clause] ...] new-linestructured-block  
```  
  
 Предложение является одним из следующих:  
  
 **закрытый (** *списка переменной* **)**  
  
 **firstprivate (** *списка переменной* **)**  
  
 **copyprivate (** *списка переменной* **)**  
  
 **nowait**  
  
 Отсутствует неявное барьера после **один** создать, если **nowait** указано предложение.  
  
 Ограничения для **одного** директивы, следующим образом:  
  
-   Только один **nowait** предложение могут отображаться на **одного** директивы.  
  
-   **Copyprivate** предложение не должны использоваться с **nowait** предложения.  
  
## <a name="cross-references"></a>Перекрестные ссылки:  
  
-   **закрытый**, **firstprivate**, и **copyprivate** предложений, в разделе [раздел 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) на странице 25.