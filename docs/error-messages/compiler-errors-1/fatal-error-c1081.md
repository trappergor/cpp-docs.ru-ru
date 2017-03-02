---
title: "Неустранимая ошибка C1081 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1081
dev_langs:
- C++
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 39c3a48e3fa01eb9bf2f357df73ef0bb466d1b10
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1081"></a>Неустранимая ошибка C1081
«символ»: слишком длинное имя файла  
  
 Длина пути файла превышает `_MAX_PATH` (в STDLIB.h задана как 260 символов). Сократите имя файла.  
  
 При вызове CL.exe с коротким именем файла, компилятор может потребоваться создать полный путь. Например `cl -c myfile.cpp` может привести к созданию компилятором:  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```
