---
title: Неустранимая ошибка C1852 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1852
dev_langs:
- C++
helpviewer_keywords:
- C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d11160eea5e978a0c1ef67255d4e96b48fe2d101
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33199515"
---
# <a name="fatal-error-c1852"></a>Неустранимая ошибка C1852
"имя_файла" не является допустимым файлом предкомпилированного заголовка  
  
 Файл не является предкомпилированным заголовком.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Указан недопустимый файл с **/Yu** или **#pragma hdrstop**.  
  
2.  Если не указано иное, компилятор предполагает расширение файла PCH.