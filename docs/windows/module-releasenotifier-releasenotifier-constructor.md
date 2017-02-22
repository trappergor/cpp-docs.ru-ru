---
title: "Конструктор Module::ReleaseNotifier::ReleaseNotifier | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseNotifier, конструктор"
ms.assetid: 889a3c9a-2366-44a1-ba7d-a59c1885e7f3
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Конструктор Module::ReleaseNotifier::ReleaseNotifier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Инициализирует новый экземпляр класса Module::ReleaseNotifier.  
  
## Синтаксис  
  
```cpp  
ReleaseNotifier(bool release) throw();  
```  
  
#### Параметры  
 `release`  
 `true` для удаления этого экземпляра, когда вызывается метод Release; `false`, чтобы не удалять этот экземпляр.  
  
## Исключения  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс Module::ReleaseNotifier](../Topic/Module::ReleaseNotifier%20Class.md)