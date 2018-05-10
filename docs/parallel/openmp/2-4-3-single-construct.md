---
title: 2.4.3 одна конструкция | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db3f9ca834fb3f35c95732698fd02e16f31b4225
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
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