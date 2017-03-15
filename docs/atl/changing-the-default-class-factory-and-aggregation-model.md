---
title: "Changing the Default Class Factory and Aggregation Model | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregation [C++], aggregation models"
  - "aggregation [C++], использование языка ATL"
  - "CComClassFactory class, making the default"
  - "CComCoClass class, default class factory and aggregation model"
  - "class factories, изменение значения по умолчанию"
  - "default class factory"
  - "default class factory, ATL - библиотека"
  - "по умолчанию [C++], aggregation model in ATL"
  - "по умолчанию [C++], class factory"
ms.assetid: 6e040e95-0f38-4839-8a8b-c9800dd47e8c
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Changing the Default Class Factory and Aggregation Model
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CComCoClass](../Topic/CComCoClass%20Class.md) использования библиотеки ATL по умолчанию указать фабрику класса и агрегирование для объекта модели.  `CComCoClass` определяет следующие 2 макроса:  
  
-   [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md) объявляет фабрику класса для [CComClassFactory](../atl/reference/ccomclassfactory-class.md).  
  
-   [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md) объявляет, что объект может быть агрегированными.  
  
 Можно переопределить одно из этих значений по умолчанию, указав другой макрос в определении класса.  Например, чтобы использовать [CComClassFactory2](../Topic/CComClassFactory2%20Class.md) вместо `CComClassFactory` укажите макрос [DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md):  
  
 [!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/CPP/changing-the-default-class-factory-and-aggregation-model_1.h)]  
  
 2 Остальных макросов, которые определяют фабрику класса [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) и [DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md).  
  
 Библиотеки ATL также использует механизм `typedef` чтобы реализовать расширение функциональности по умолчанию.  Например, макрос `DECLARE_AGGREGATABLE` использует `typedef`, чтобы определить тип **\_CreatorClass**, которое затем ссылаются на протяжении библиотеки ATL.  Обратите внимание, что в производном классе `typedef` с помощью этих же именем в результаты `typedef` базового типа библиотеки ATL с помощью определения и переопределить функциональности по умолчанию.  
  
## См. также  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)   
 [Aggregation and Class Factory Macros](../atl/reference/aggregation-and-class-factory-macros.md)