---
title: Неустранимая ошибка NMAKE U1064 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1064
dev_langs:
- C++
helpviewer_keywords:
- U1064
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5573943fc2c274d48768933a634b2c052361a8f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1064"></a>Неустранимая ошибка NMAKE U1064
MAKEFILE не найден и не указан целевой объект  
  
 В командной строке (NMAKE) не указан файл makefile или целевой объект и текущий каталог не содержит файл makefile.  
  
 В программе NMAKE необходимо либо makefile или целевой объект командной строки (или оба). Для предоставления файла makefile (NMAKE), задайте параметр /F или поместите файл makefile в текущем каталоге. С помощью правило определения, если не указан файл makefile (NMAKE) можно создать целевой объект командной строки.