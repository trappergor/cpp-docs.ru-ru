---
title: "Ошибка средств компоновщика LNK1106 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1106
dev_langs: C++
helpviewer_keywords: LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b97196ebed51c21e40fa74ab1b80d23f3c49eec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1106"></a>Ошибка средств компоновщика LNK1106
Недопустимый файл или нет места на диске: не удается обратиться к расположению  
  
 Средство не удалось чтение или запись `location` в файле памяти.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Диск заполнен.  
  
     Освободите место на диске и связывать их еще раз.  
  
2.  Попытка выполнить компоновку по сети.  
  
     Некоторые сети не полностью поддерживают сопоставленные в памяти файлы, используемые компоновщиком. Попытайтесь выполните компоновку на локальном диске.  
  
3.  Поврежденный блок на диске.  
  
     Несмотря на то, что операционная система и оборудование диска должны обнаруживать такие ошибки, можно запустить программу проверки диска.  
  
4.  Недостаточно места в куче.  
  
     В разделе [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) для получения дополнительной информации.