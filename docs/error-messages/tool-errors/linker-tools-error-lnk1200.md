---
title: "Ошибка средств компоновщика LNK1200 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1200
dev_langs: C++
helpviewer_keywords: LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 70bf262d4f99c807e3488c1f9b2ed9e73b1eb715
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1200"></a>Ошибка средств компоновщика LNK1200
Ошибка при чтении базы данных программы «имя_файла»  
  
 Не удается прочитать базу данных программы (PDB).  
  
 Эта ошибка может быть вызвано повреждение файла.  
  
 Если `filename` является PDB для объектного файла, перекомпилировать файл объекта с помощью [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
 Если `filename` является PDB-ФАЙЛ для основного выходного файла, и эта ошибка возникает во время инкрементной компоновки, удалите PDB-ФАЙЛ и повторного создания связей.