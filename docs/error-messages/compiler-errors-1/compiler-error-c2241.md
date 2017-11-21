---
title: "Ошибка компилятора C2241 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2241
dev_langs: C++
helpviewer_keywords: C2241
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0625c4682ff44904ce166d370ec797c1d147ad02
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2241"></a>Ошибка компилятора C2241
"идентификатор": доступ к члену ограничен  
  
 Код пытается получить доступ к закрытому или защищенному члену.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Измените уровень доступа члена.  
  
2.  Объявите этот член в качестве `friend` функции доступа.