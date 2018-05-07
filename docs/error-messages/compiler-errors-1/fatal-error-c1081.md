---
title: Неустранимая ошибка C1081 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1081
dev_langs:
- C++
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b5ea18ff3f2714d9621d4372cf541be2f9b225a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1081"></a>Неустранимая ошибка C1081
«символ»: слишком длинное имя файла  
  
 Длина пути файла превышает `_MAX_PATH` (определяемые STDLIB.h как 260 символов). Сократите имя файла.  
  
 При вызове CL.exe с коротким именем файла, компилятор может потребоваться создать полный путь. Например `cl -c myfile.cpp` может привести к созданию компилятором:  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```