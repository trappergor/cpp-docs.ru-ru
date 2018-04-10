---
title: 2.4.2 конструкция sections | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6e5b755e95e9bbbb78d6ab13cd09732f9c9aee3d
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/10/2018
---
# <a name="242-sections-construct"></a>2.4.2 Конструкция sections
**Разделы** директива идентифицирует noniterative конструкции совместной работы, указывающий набор конструкций, которые будет разделен между потоками в команде. В каждом разделе выполняется потоком в группе один раз. Синтаксис **разделы** директивы таков:  
  
```  
#pragma omp sections [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-linestructured-block ]  
...  
}  
```  
  
 Предложение является одним из следующих:  
  
 **private(** *variable-list* **)**  
  
 **firstprivate(** *variable-list* **)**  
  
 **lastprivate(** *variable-list* **)**  
  
 **Уменьшение (** *оператор* **:***списка переменной* **)**   
  
 **nowait**  
  
 Каждый раздел предшествует **раздел** директивы, несмотря на то что **раздел** директива является необязательным для первого раздела. **Раздел** директивы должен находиться внутри лексическая область **разделы** директивы. В конце отсутствует неявное барьера **разделы** создать, если **nowait** указано.  
  
 Ограничения для **разделы** директивы, следующим образом:  
  
-   Объект **раздел** директива не должна находиться за пределами лексическая область **разделы** директивы.  
  
-   Только один **nowait** предложение могут отображаться на **разделы** директивы.  
  
## <a name="cross-references"></a>Перекрестные ссылки:  
  
-   **закрытый**, **firstprivate**, **lastprivate**, и **сокращения** предложений, в разделе [раздел 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) на странице 25.