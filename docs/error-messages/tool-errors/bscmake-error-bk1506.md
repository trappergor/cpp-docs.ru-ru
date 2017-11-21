---
title: "Ошибка BSCMAKE BK1506 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK1506
dev_langs: C++
helpviewer_keywords: BK1506
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c792f28b29ca9abf8594fbe6e351c4782b149a61
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="bscmake-error-bk1506"></a>Ошибка BSCMAKE BK1506
не удается открыть файл «имя_файла» [: причина]  
  
 BSCMAKE не удается открыть файл.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Файл заблокирован другим процессом. Если `reason` говорит **отказано в разрешении**, браузер, использует этот файл. Закройте окно «Обзор» и повторите попытку сборки.  
  
2.  Диск переполнен.  
  
3.  Аппаратная ошибка.  
  
4.  Указанный выходной файл имеет имя, совпадающее с именем существующий подкаталог.