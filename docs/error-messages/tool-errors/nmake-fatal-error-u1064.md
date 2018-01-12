---
title: "Неустранимая ошибка NMAKE U1064 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1064
dev_langs: C++
helpviewer_keywords: U1064
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 20b6c767145176c459d0b70d96842223218cd0b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1064"></a>Неустранимая ошибка NMAKE U1064
MAKEFILE не найден и не указан целевой объект  
  
 В командной строке (NMAKE) не указан файл makefile или целевой объект и текущий каталог не содержит файл makefile.  
  
 В программе NMAKE необходимо либо makefile или целевой объект командной строки (или оба). Для предоставления файла makefile (NMAKE), задайте параметр /F или поместите файл makefile в текущем каталоге. С помощью правило определения, если не указан файл makefile (NMAKE) можно создать целевой объект командной строки.