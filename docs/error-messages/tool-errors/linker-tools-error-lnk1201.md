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
ms.workload: cplusplus
ms.openlocfilehash: 44e2ad811645889cd655bf297f6f8b9492574def
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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