---
title: "Setting Up a Static Link to the Registrar Code (C++ Only) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "связывание [C++], to ATL Registrar code"
  - "statically linking to ATL Registrar code"
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Setting Up a Static Link to the Registrar Code (C++ Only)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Клиенты C\+\+ могут создать статическая ссылка в код регистратора.  Статическое связывание средства синтаксического анализа регистратора добавляет приблизительно 5K на построение выпуска.  
  
 Самый простой способ настроить статическое связывание предполагает, что определяет [DECLARE\_REGISTRY\_RESOURCEID](../Topic/DECLARE_REGISTRY_RESOURCEID.md) в объявлении объекта.  \(По умолчанию это спецификация, используемой библиотеки ATL\).  
  
### Создание статическая ссылка с помощью DECLARE\_REGISTRY\_RESOURCEID  
  
1.  Укажите [\/D](../build/reference/d-preprocessor-definitions.md)`_ATL_STATIC_REGISTRY` вместо \/D **\_ATL\_DLL**.  
  
2.  Выполните компиляцию заново.  
  
## См. также  
 [Компонент реестра \(регистратор\)](../atl/atl-registry-component-registrar.md)