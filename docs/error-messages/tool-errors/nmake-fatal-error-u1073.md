---
title: "Неустранимая ошибка NMAKE U1073 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1073
dev_langs: C++
helpviewer_keywords: U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: faae317df44560991a88d47ec7f123e6a8126429
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1073"></a>Неустранимая ошибка NMAKE U1073
не знаете, как сделать «targetname»  
  
 Указанный целевой объект не существует, и нет команды для выполнения или применяемое правило.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Проверьте правильность написания имени целевого объекта.  
  
2.  Если *targetname* является псевдоцелью, укажите его в качестве цели в другом блоке описания.  
  
3.  Если *targetname* является вызовом макроса, убедитесь, что оно не разворачивается до пустой строки.