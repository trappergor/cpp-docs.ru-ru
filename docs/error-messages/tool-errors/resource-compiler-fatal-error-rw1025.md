---
title: "Неустранимая ошибка компилятора ресурсов RW1025 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RW1025
dev_langs: C++
helpviewer_keywords: RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 487968f8a1242dd4c36e4bbd9b4ede08a5ab4d95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rw1025"></a>Неустранимая ошибка компилятора ресурсов RW1025
Недостаточно памяти для кучи дальней  
  
 Проверьте наличие резидентной программное обеспечение, которое могут занимать слишком много места. Чтобы узнать, какой объем памяти, у вас есть используйте программу CHKDSK.  
  
 При создании большого файла ресурса разделите два файла описания ресурсов. После создания двух RES-файлов используйте командной строки MS-DOS для их соединения:  
  
```  
copy first.res /b + second.res /b full.res  
```