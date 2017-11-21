---
title: "2.4.2 конструкция sections | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 22aa4cc1bde59234d70803c2e878d3fbf83f499e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
  
 **закрытый (** *списка переменной* **)**  
  
 **firstprivate (** *списка переменной* **)**  
  
 **lastprivate (** *списка переменной* **)**  
  
 **Уменьшение (** *оператор* **:***списка переменной* **)**   
  
 **nowait**  
  
 Каждый раздел предшествует **раздел** директивы, несмотря на то что **раздел** директива является необязательным для первого раздела. **Раздел** директивы должен находиться внутри лексическая область **разделы** директивы. В конце отсутствует неявное барьера **разделы** создать, если **nowait** указано.  
  
 Ограничения для **разделы** директивы, следующим образом:  
  
-   Объект **раздел** директива не должна находиться за пределами лексическая область **разделы** директивы.  
  
-   Только один **nowait** предложение могут отображаться на **разделы** директивы.  
  
## <a name="cross-references"></a>Перекрестные ссылки:  
  
-   **закрытый**, **firstprivate**, **lastprivate**, и **сокращения** предложений, в разделе [раздел 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) на странице 25.