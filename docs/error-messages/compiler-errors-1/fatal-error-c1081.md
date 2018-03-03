---
title: "Неустранимая ошибка C1081 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1081
dev_langs:
- C++
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8bac4aaf0d4aebcbc34f74b6ccb91170fd4224e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1081"></a>Неустранимая ошибка C1081
«символ»: слишком длинное имя файла  
  
 Длина пути файла превышает `_MAX_PATH` (определяемые STDLIB.h как 260 символов). Сократите имя файла.  
  
 При вызове CL.exe с коротким именем файла, компилятор может потребоваться создать полный путь. Например `cl -c myfile.cpp` может привести к созданию компилятором:  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```