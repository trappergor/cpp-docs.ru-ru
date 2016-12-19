---
title: "Форматы даты и времени в 32-разрядных операционных системах Windows | Microsoft Docs"
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
  - "vc.time"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "32-разрядная Windows"
ms.assetid: ef1589db-84d7-4b24-8799-7c7a22cfe2bf
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Форматы даты и времени в 32-разрядных операционных системах Windows
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Дата и время файла хранятся отдельно, используя целые числа без знака как битовые поля.  Время и дата файла упакованы следующим образом:  
  
### Время  
  
|Позиция бита:|0   1   2   3   4|5   6   7   8   9   A|B   C   D   E   F|  
|-------------------|-----------------------|---------------------------|-----------------------|  
|Длина:|5|6|5|  
|Содержание|hours|минуты|Интервалы по 2 секунды|  
|Диапазон значений:|0–23|0–59|0\-29 в интервалах по 2 секунды|  
  
### дата.  
  
|Позиция бита:|0   1   2   3   4   5   6|7   8   9   A|B   C   D   E   F|  
|-------------------|-------------------------------|-------------------|-----------------------|  
|Длина:|7|4|5|  
|Содержание|year|month|день|  
|Диапазон значений:|0–119|1–12|1–31|  
||\(относительно 1980\)|||  
  
## См. также  
 [Глобальные константы](../c-runtime-library/global-constants.md)