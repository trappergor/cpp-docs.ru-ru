---
title: "VCPROFILE_ALLOC_SCALE | Microsoft Docs"
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
  - "VCPROFILE_ALLOC_SCALE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VCPROFILE_ALLOC_SCALE - переменная среды"
ms.assetid: 5cb5ce27-f9b8-489b-b46c-d6e9bcab2d34
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# VCPROFILE_ALLOC_SCALE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Изменение объема памяти, выделенного под данные профиля.  
  
## Синтаксис  
  
```  
VCPROFILE_ALLOC_SCALE=scale_value  
```  
  
#### Параметры  
 `scale_value`  
 Значение масштаба для объема памяти, необходимой для запуска проверочных скриптов.  Значение по умолчанию — 1.  
  
## Заметки  
 В отдельных случаях при запуске проверочных скриптов возникает нехватка памяти для сбора данных профиля.  В таких случаях можно увеличить объем памяти с помощью `VCPROFILE_ALLOC_SCALE`.  
  
 Если во время проверки выводится сообщение об ошибке, связанной с нехваткой памяти, следует присвоить параметру `VCPROFILE_ALLOC_SCALE` большее значение, которое позволит завершить проверку без ошибок, связанных с нехваткой памяти.  
  
## Пример  
  
```  
set VCPROFILE_ALLOC_SCALE=2  
```  
  
## См. также  
 [Переменные среды для профильной оптимизации](../../build/reference/environment-variables-for-profile-guided-optimizations.md)