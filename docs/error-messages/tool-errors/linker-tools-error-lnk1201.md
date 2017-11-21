---
title: "Ошибка средств компоновщика LNK1201 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1201
dev_langs: C++
helpviewer_keywords: LNK1201
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 344f56eb3097bad447d9a0b12a0c5aac6f68b119
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1201"></a>Ошибка средств компоновщика LNK1201
Ошибка при записи в базу данных программы «ИмяФайла»; Проверьте недостаточно места на диске, недопустимый путь или недостаточно прав  
  
 СВЯЗЬ не удается записать в базу данных программы (PDB) для выходного файла.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Файл поврежден. Удалите PDB-файл и повторно выполнить компоновку.  
  
2.  Недостаточно места на диске для записи файла.  
  
3.  Диск недоступен из-за проблемы с сетью.  
  
4.  Отладчик активна в программу, которую вы пытаетесь подключиться.  
  
5.  Недостаточно места в куче.  В разделе [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) для получения дополнительной информации.