---
title: "Using IDispEventImpl | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDispEventImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventImpl class, использование"
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Using IDispEventImpl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При использовании `IDispEventImpl` для обработки событий, необходимо следующее:  
  
-   Создайте производный класс от [IDispEventImpl](../atl/reference/idispeventimpl-class.md).  
  
-   Добавьте [сопоставление приемника событий](../Topic/BEGIN_SINK_MAP.md) к классу.  
  
-   Добавьте записи к сопоставлению приемника событий, используя макрос [SINK\_ENTRY](../Topic/SINK_ENTRY.md) или [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY_EX.md).  
  
-   Реализуйте методы что нужно знать обработки.  
  
-   Посоветуйте и unadvise источник события.  
  
## Пример  
 Пример в выставками, как обработать событие **DocumentChange** сгоренное объектом **Приложение** слова.  Это событие задается в качестве метода для **ApplicationEvents** dispinterface.  
  
 Пример из [Образец ATLEventHandling](../top/visual-cpp-samples.md).  
  
 `[`  
  
 `uuid(000209F7-0000-0000-C000-000000000046),`  
  
 `hidden`  
  
 `]`  
  
 `dispinterface ApplicationEvents {`  
  
 `properties:`  
  
 `methods:`  
  
 `[id(0x00000001), restricted, hidden]`  
  
 `void Startup();`  
  
 `[id(0x00000002)]`  
  
 `void Quit();`  
  
 `[id(0x00000003)]`  
  
 `void DocumentChange();`  
  
 `};`  
  
 В примере используется `#import` для создания необходимых файлов заголовка из библиотеки типов слова.  Если требуется использовать этот пример с другими версиями слов, следует указать правильный файлу mso dll.  Например, предоставляемые mso9.dll office 2000 и Office XP предоставляет mso.dll.  Этот код в файл stdafx.h упрощен:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/CPP/using-idispeventimpl_1.h)]  
  
 В следующем примере кода отображается в NotSoSimple.h.  Соответствующий код отметить комментариями:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/CPP/using-idispeventimpl_2.h)]  
  
## См. также  
 [Обработка событий](../Topic/Event%20Handling%20and%20ATL.md)   
 [Образец ATLEventHandling](../top/visual-cpp-samples.md)