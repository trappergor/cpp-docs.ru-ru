---
title: "Aggregation and Class Factory Macros | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregation [C++], ATL macros"
  - "class factories, ATL macros"
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
caps.latest.revision: 17
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Aggregation and Class Factory Macros
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Эти макросы предоставляют способы мониторинга статистическую обработку и объявления фабрики класса.  
  
|||  
|-|-|  
|[DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md)|Объявляет, что объект может быть агрегирован \(по умолчанию\).|  
|[DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md)|Объявляет фабрику класса для [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), фабрикой класса значения по умолчанию библиотеки ATL.|  
|[DECLARE\_CLASSFACTORY\_EX](../Topic/DECLARE_CLASSFACTORY_EX.md)|Объявляет объекта фабрики класса для класса фабрикой.|  
|[DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md)|Объявляет [CComClassFactory2](../Topic/CComClassFactory2%20Class.md) чтобы быть фабрикой класса.|  
|[DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md)|Объявляет [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) чтобы быть фабрикой класса.|  
|[DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md)|Объявляет [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) чтобы быть фабрикой класса.|  
|[DECLARE\_GET\_CONTROLLING\_UNKNOWN](../Topic/DECLARE_GET_CONTROLLING_UNKNOWN.md)|Объявляет виртуальную функцию `GetControllingUnknown`.|  
|[DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)|Объявляет, что объект не могут быть агрегированными.|  
|[DECLARE\_ONLY\_AGGREGATABLE](../Topic/DECLARE_ONLY_AGGREGATABLE.md)|Объявляет, что этот объект должен быть агрегированными.|  
|[DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md)|Проверяет значение внешнего неизвестным и объявляется объект aggregatable или статистическая обработка невозможна, например соответствующий.|  
|[DECLARE\_PROTECT\_FINAL\_CONSTRUCT](../Topic/DECLARE_PROTECT_FINAL_CONSTRUCT.md)|Защищает внешний объект из удаления при создании внутреннего объекта.|  
|[DECLARE\_VIEW\_STATUS](../Topic/DECLARE_VIEW_STATUS.md)|Указывает флаги **VIEWSTATUS** в контейнер.|  
  
## См. также  
 [Macros](../../atl/reference/atl-macros.md)