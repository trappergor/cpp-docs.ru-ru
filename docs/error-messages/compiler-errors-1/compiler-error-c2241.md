---
title: Ошибка компилятора C2241 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2241
dev_langs:
- C++
helpviewer_keywords:
- C2241
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d1a4404d3f7e60adc2d8f9ff0c8ccb3d154b26d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2241"></a>Ошибка компилятора C2241
"идентификатор": доступ к члену ограничен  
  
 Код пытается получить доступ к закрытому или защищенному члену.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Измените уровень доступа члена.  
  
2.  Объявите этот член в качестве `friend` функции доступа.