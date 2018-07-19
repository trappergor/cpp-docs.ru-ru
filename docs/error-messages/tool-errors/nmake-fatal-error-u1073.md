---
title: Неустранимая ошибка NMAKE U1073 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1073
dev_langs:
- C++
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dde9ca2f4a15edf6599dcc31b39d9411645f2a6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33316310"
---
# <a name="nmake-fatal-error-u1073"></a>Неустранимая ошибка NMAKE U1073
не знаете, как сделать «targetname»  
  
 Указанный целевой объект не существует, и нет команды для выполнения или применяемое правило.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Проверьте правильность написания имени целевого объекта.  
  
2.  Если *targetname* является псевдоцелью, укажите его в качестве цели в другом блоке описания.  
  
3.  Если *targetname* является вызовом макроса, убедитесь, что оно не разворачивается до пустой строки.